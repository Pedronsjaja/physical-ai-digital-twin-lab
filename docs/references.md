# References and evidence boundaries

Reviewed 2026-10-26. Official documentation supports design decisions, not experimental outcomes.

| Source | Problem / method | Variables and application | Limits / reproduction |
|---|---|---|---|
| [Gazebo ROS compatibility](https://gazebosim.org/docs/harmonic/ros_installation/) | Select a supported ROS/Gazebo pairing | Jazzy/Harmonic retained for consistency with GAIA | Compatibility guidance, not a tested installation in this task |
| [ROS QoS source, Jazzy](https://github.com/ros2/ros2_documentation/blob/jazzy/source/Concepts/Intermediate/About-Quality-of-Service-Settings.rst) | Offered/requested policy compatibility | Reliability, history, durability, deadline and lifespan in future tests | docs.ros.org page blocked this session; official repository source was read. QoS does not prove deadline compliance |
| [ros2_control hardware component guide](https://control.ros.org/jazzy/doc/ros2_control/hardware_interface/doc/writing_new_hardware_component.html) | Lifecycle and read/write plugin boundary | Future bounded actuator integration | Guide inspected; no plugin implemented or compiled |
| [GAIA driver](https://github.com/Pedronsjaja/gaia-lx225-buslinker/blob/main/servo_testbench.py) | Serial protocol and host-side feedback | angle_deg, voltage_v, temperature_c, estimated velocity, host monotonic time after position reply | Software inspection and mocked tests; no new physical validation |
| [GAIA CAD contract](https://github.com/Pedronsjaja/gaia-humanoid-structure/blob/main/docs/modelo-gaia.md) | Identify mechanical state before model export | Mass, inertia, axes, zero, limits | Missing values remain UNKNOWN; CAD license provenance unresolved |
| [Isaac Sim](https://github.com/isaac-sim/IsaacSim) | Future high-fidelity simulation evaluation | Rendering/sensors and interoperability when justified | Not installed; runtime/assets have terms beyond a single repository license label |
| [Isaac Lab](https://github.com/isaac-sim/IsaacLab) | Future robot-learning experiment framework | Baselines, seeds, task-specific evaluation | No RL/IL/VLA implemented or results inferred |
| [OpenUSD](https://github.com/PixarAnimationStudios/OpenUSD) | Scene description/interchange | Future CAD/scene pipeline | Asset interchange does not identify dynamics or synchronize hardware |

## Literature lead — bibliographic verification only

Werner Kritzinger, Matthias Karner, Georg Traar, Jan Henjes, Wilfried Sihn.
“Digital Twin in manufacturing: A categorical literature review and classification.”
IFAC-PapersOnLine 51(11), 1016–1022 (2018).
DOI: [10.1016/j.ifacol.2018.08.474](https://doi.org/10.1016/j.ifacol.2018.08.474).

Title/authors/DOI were cross-checked through bibliographic records; publisher full text was blocked (403). Full methodological/results review: NOT_VERIFIED. Do not cite this entry as evidence of measured performance or claim a full paper review.
Question for later reading: how data-flow integration distinguishes models, shadows and twins. The lab's state-contract terminology is explicitly a working definition.
Equipment, numerical outcomes and reproducible hardware procedure from this paper: not established in this review.

## Reuse assessment

The [open-source catalog](open-source-projects.md) records purpose, maturity assessment, activity, license metadata, useful boundary and limitations. No third-party source or CAD was copied into this lab. Pin an exact revision and review its LICENSE/NOTICE and dependency terms before reuse.
