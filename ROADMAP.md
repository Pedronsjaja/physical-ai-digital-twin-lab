# Research and implementation roadmap

All milestones below are **Planned**. Version labels are acceptance milestones, not releases or dates. Documentation exists; runtime implementation does not.

| Milestone | Deliverable | Acceptance evidence |
|---|---|---|
| v0.1 — Virtual Engineering Lab | Gazebo world with room, bench, objects, lighting and physics; pinned setup instructions | Clean-machine launch; world loads; gravity/contact smoke check; logs and software versions |
| v0.2 — Robotics | One fixed-base revolute actuator and a virtual state source; arm/mobile robot only after this | Joint axis, limits and model parameters reviewed; observed state changes after command |
| v0.3 — ROS 2 Integration | Package, launch, TF, joint states, topics; services for configuration and sensor topics only where needed | colcon build/test; topic/type/QoS inventory; simulation timestamps; clean shutdown |
| v0.4 — Digital Twin | Identified asset, state mapping and physical → ROS 2 → virtual synchronization; guarded reverse command path later | Calibrated units/zero/sign; alignment method; divergence logs; distinguish shadow from validated bidirectional twin |
| v0.5 — Communication Research Lab | Fast DDS versus Cyclone DDS methodology and reproducible benchmark | Fixed workload/version/QoS; latency, jitter, loss definitions, CPU/RAM, bandwidth, update rate and synchronization RMSE; raw data and uncertainty |
| v0.6 — Industrial Communication | One justified OPC UA/open62541 gateway; MQTT/Mosquitto evaluated separately | Industrial device → OPC UA → gateway → ROS 2/DDS → virtual state; type/unit/timestamp mapping, disconnect/reconnect and security configuration tests |
| v0.7 — Autonomous Systems | One perception/planning/navigation behavior with a baseline | Repeatable scenario, success/failure criteria, independent safety limits and failure analysis |
| v0.8 — Physical AI | Evaluate RL, imitation learning, VLA or AI agents for one defined task; select only justified methods | Baseline comparison, dataset provenance, seeds, compute budget, held-out evaluation; no claimed gain without results |
| v0.9 — Sim-to-Real | Shared state/command semantics with separate simulation and hardware adapters | Contract and fault tests across modes; model mismatch quantified; no silent REAL/SIMULATED switch |
| v1.0 — Physical Robotic Platform | LX-225 + BusLinker as first candidate; GAIA humanoid only after single-joint acceptance | Identified setup, operator, stop strategy, bounded motion, raw logs and reproducible comparison |

## First implementation slice

Deliver v0.1–v0.3 only as needed for one virtual actuator. Avoid building a detailed room or a whole humanoid before joint feedback is verified.
Acceptance: one command changes the observed simulated joint state; stale/no-feedback fails the check; logs identify SIMULATED origin and clock domain.
Numeric tolerances must be justified by the chosen synthetic model and solver before running the test. They must not be presented as LX-225 specifications.

## Admission gates

- Isaac Sim/OpenUSD: require a task where rendering, sensor fidelity or asset interchange improves the experiment; compare against the Gazebo baseline. Confirm GPU/runtime/license constraints then.
- Isaac Lab: require a defined learning task, baseline and compute budget.
- Jetson/edge inference: require measured latency/compute/power constraints and confirmed hardware.
- CAD/CAE + AI: secondary; validate dimensions and physics independently of generated geometry.
- Physical integration: read-only acquisition first. Commands require mechanical/electrical limits, operator and independent stopping means.
