# Proposed state contract

**Documented proposal, not a ROS interface implementation.**

Use sensor_msgs/msg/JointState for standard joint observation, with radians and rad/s, and a separate provenance/diagnostics envelope or custom message if the benchmark requires correlation fields. JointState alone has no source/sequence/clock-domain fields. Never label commanded position as measured position.

| Field/channel | Unit | Origin / quality | Timestamp and range |
|---|---|---|---|
| joint_name, asset_id, run_id, sequence | none | Stable identity; sequence unique within run/source | New run on process restart |
| position_rad | rad | REAL servo feedback or SIMULATED joint observation | Explicit source time; calibrated zero/sign; mechanical range UNKNOWN |
| velocity_rad_s | rad/s | ESTIMATED from physical samples or simulator-provided SIMULATED value | Derivation interval recorded; first derivative unavailable |
| voltage_v | V | REAL serial feedback | Separate read time if available; valid range from confirmed datasheet |
| temperature_c | °C | REAL serial feedback; Celsius explicitly retained | Separate read time; not inferred from position time |
| effort_nm, current_a | N·m, A | UNKNOWN / NOT_MEASURED for current driver | Omit or flag unavailable; do not fill zero |
| source_time, receive_time, clock_domain | s or integer ns, declared | Host receive-after-read, simulator time or synchronized wall time | Never subtract unlike clocks |
| quality, age, nominal_rate, observed_rate | enum, s, Hz, Hz | VALID / STALE / INVALID / TIMEOUT; rate metadata | Frequency and freshness budget TBD before experiment |

For direct coupling:
theta_joint_rad = sign × (angle_servo_deg − zero_servo_deg) × pi/180.
For transmission ratio r = servo rotation / joint rotation, divide by r; define sign and zero explicitly. r and zero are UNKNOWN until identified.

Keep command records separate: command_id, target position, issue time, deadline, allowed range and acceptance/rejection. A matching ID does not prove the actuator reached its target.

## Clock contract

Initial software communication measurements use one host monotonic clock domain. Across hosts, record synchronization method and offset/uncertainty; otherwise report RTT, not one-way latency. Simulation time may pause/reset/run slower than wall time. Store both simulator time and host receipt time with run epochs. Do not compare raw /clock against host monotonic time.

## Working terminology

- Simulation: computation of model behavior; may have no physical counterpart.
- Digital model: identified digital representation without automatic physical data exchange.
- Digital shadow: automated physical → digital update.
- Digital Twin: within this project's declared scope, identified physical/digital pair with validated bidirectional interaction and documented synchronization limits.

This is an operational taxonomy, not a claim that all literature uses the same definition.
