# Architecture — proposed, not implemented

## Responsibilities

| Boundary | Responsibility | Initial choice / future option |
|---|---|---|
| Physical | Sensor/actuator identification, safe acquisition and bounded commands | LX-225/BusLinker candidate; ESP32 and Jetson not assumed available |
| Communication | Typed state, provenance, freshness, transport and recording | ROS 2 Jazzy with a DDS RMW; OPC UA/MQTT are future gateways |
| Simulation | Independent model evolution and observed joint feedback | Gazebo Harmonic initially; Isaac Sim/OpenUSD optional later |
| Intelligence | Consume validated state, propose actions within a separate command gate | No policy or agent implemented |
| Analysis | Preserve raw data, align clocks, compare states, report uncertainty | Offline analysis before closed-loop adaptation |

ROS 2 ordinarily uses an RMW abstraction over DDS; DDS is not an extra serial hop inserted after a ROS node. Gazebo's own transport requires a bridge or simulator/control integration.

## Staged data flow

1. Virtual source → ROS state → recorder, all explicitly SIMULATED.
2. Existing Python driver → future read-only ROS adapter → virtual mirror and recorder.
3. Independently simulated response and measured physical response under a common bounded command → aligned error analysis.
4. Only after safety acceptance: supervised command gate → actuator adapter → physical device.

Only one process owns the serial port. Serial polling is blocking and must not be placed in a time-critical control update loop without a bounded design and measured timing.

## Existing driver integration

ServoState already includes angle_deg, voltage_v, temperature_c, velocity_dps and position_time_s.
The position timestamp is host monotonic time after the position reply. Voltage and temperature are read later; this is not a simultaneous sensor snapshot. velocity_dps is finite-difference ESTIMATED; effort/current are unavailable.

Stage one wraps read-only Python acquisition. Stage two evaluates a ros2_control ActuatorInterface/SystemInterface with lifecycle, read/write, error handling and bounded timeouts. The normal plugin boundary is a compiled library; a Python driver is not automatically a ros2_control plugin. Compare a C++ driver against a process-separated bridge only when requirements justify it.

## Logical expansion, not empty scaffolding

Create ros2_ws/src when an actual package is added; simulation/gazebo for executable assets; hardware/lx225 for reviewed configuration; communication/dds and experiments for implemented runners; benchmarks for scripts tied to raw data. Defer isaac_sim, usd, esp32, opcua and mqtt directories until useful content exists.

## Failure behavior

Invalid, stale, reordered and missing samples retain distinct statuses. No value substitution with zero. No automatic physical actuation at startup/reconnect.
A stop packet is not an independent emergency stop. Define fault reaction for the confirmed assembly; dropping torque can itself be unsafe under gravity.
