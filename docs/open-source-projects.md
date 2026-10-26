# Open-source projects to follow

Reviewed 2026-10-26. Primary priority: ROS 2 through OpenUSD. Secondary: FreeCAD, MCP candidates, build123d and OpenModelica. Difficulty and maturity below are [ESTIMATED] for the scoped contribution, not certification. GitHub last-push dates describe repository activity, not support guarantees. License metadata is a starting point; NOASSERTION/UNKNOWN requires reading exact upstream terms before reuse.

## ROS 2

- Source: [ros2/ros2](https://github.com/ros2/ros2).
- Purpose / lab boundary: Middleware/client-library ecosystem; state transport and tooling.
- Technologies: C++, Python, ament/colcon, RMW.
- Maturity / contribution path: Established modular ecosystem; documentation reproduction and minimal bug reports.
- Difficulty: Low for docs; high for core timing.
- Last push reported: 2026-10-20T18:12:35Z; license metadata: UNKNOWN.
- Limitation: Multi-package licensing; metarepo license metadata insufficient.
- Issue: see ros2_documentation #7217 below.

## ros2_control

- Source: [ros-controls/ros2_control](https://github.com/ros-controls/ros2_control).
- Purpose / lab boundary: Lifecycle controllers and hardware interfaces.
- Technologies: C++, pluginlib, URDF, controllers.
- Maturity / contribution path: Established framework; reproduce a demo and improve interface examples.
- Difficulty: Medium.
- Last push reported: 2026-10-19T10:41:32Z; license metadata: Apache-2.0.
- Limitation: Python serial code is not a drop-in plugin.
- Issue: see ros2_control_demos #950 below.

## Gazebo

- Source: [gazebosim/gz-sim](https://github.com/gazebosim/gz-sim).
- Purpose / lab boundary: Physics and virtual sensors for baseline.
- Technologies: SDF/URDF, C++, ROS bridge.
- Maturity / contribution path: Established simulator; document reproducible actuator demos.
- Difficulty: Low–medium for docs.
- Last push reported: 2026-10-24T01:39:39Z; license metadata: Apache-2.0.
- Limitation: Simulated success does not validate physical dynamics.
- Issue: see gazebosim/docs #435 below.

## Fast DDS

- Source: [eProsima/Fast-DDS](https://github.com/eProsima/Fast-DDS).
- Purpose / lab boundary: One DDS implementation for controlled comparison.
- Technologies: C++, DDS/RTPS, XML QoS, networking.
- Maturity / contribution path: Established middleware; reproduce QoS examples and instrument workloads.
- Difficulty: Medium–high.
- Last push reported: 2026-10-23T12:00:28Z; license metadata: Apache-2.0.
- Limitation: No performance ranking inferred.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## Cyclone DDS

- Source: [eclipse-cyclonedds/cyclonedds](https://github.com/eclipse-cyclonedds/cyclonedds).
- Purpose / lab boundary: Alternative DDS implementation.
- Technologies: C, DDS, RMW, networking.
- Maturity / contribution path: Established middleware; configuration documentation and minimal reproducers.
- Difficulty: Medium–high.
- Last push reported: 2026-10-22T07:54:11Z; license metadata: NOASSERTION.
- Limitation: Check exact license files; metadata NOASSERTION.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## open62541

- Source: [open62541/open62541](https://github.com/open62541/open62541).
- Purpose / lab boundary: OPC UA server/client for future industrial gateway.
- Technologies: C, CMake, OPC UA data model.
- Maturity / contribution path: Established library; reproduce examples and document type/unit mapping.
- Difficulty: Medium.
- Last push reported: 2026-10-26T00:35:02Z; license metadata: MPL-2.0.
- Limitation: Certification/security assumptions require separate review.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## ROS-Industrial

- Source: [ros-industrial/industrial_core](https://github.com/ros-industrial/industrial_core).
- Purpose / lab boundary: Industrial robot integration reference.
- Technologies: ROS drivers, C++, industrial protocols.
- Maturity / contribution path: Established initiative; inspect active ROS 2 member projects before selecting code.
- Difficulty: Medium–high.
- Last push reported: 2024-02-02T21:35:07Z; license metadata: UNKNOWN.
- Limitation: This legacy core defaults to melodic-devel; it is not a Jazzy driver choice.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## Eclipse Ditto

- Source: [eclipse-ditto/ditto](https://github.com/eclipse-ditto/ditto).
- Purpose / lab boundary: Digital representations, connectivity and state APIs.
- Technologies: Java, HTTP, MQTT, deployment.
- Maturity / contribution path: Established framework; payload mapping examples.
- Difficulty: Medium.
- Last push reported: 2026-10-23T10:36:14Z; license metadata: EPL-2.0.
- Limitation: Not a robot physics simulator or real-time controller.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## Eclipse BaSyx

- Source: [eclipse-basyx/basyx-java-server-sdk](https://github.com/eclipse-basyx/basyx-java-server-sdk).
- Purpose / lab boundary: Asset Administration Shell integration.
- Technologies: Java, AAS, REST.
- Maturity / contribution path: Industrial ecosystem; AAS examples for documented channels.
- Difficulty: Medium.
- Last push reported: 2026-10-25T14:07:30Z; license metadata: MIT.
- Limitation: Semantic representation alone is not physical synchronization.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## NVIDIA Isaac Sim

- Source: [isaac-sim/IsaacSim](https://github.com/isaac-sim/IsaacSim).
- Purpose / lab boundary: Future simulation/rendering/sensor comparison.
- Technologies: Python, USD, compatible GPU/runtime.
- Maturity / contribution path: Active simulation platform; small reproducible scenes and documentation.
- Difficulty: Medium–high.
- Last push reported: 2026-10-23T14:17:15Z; license metadata: NOASSERTION.
- Limitation: Hardware and asset/runtime terms must be checked; not installed.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## NVIDIA Isaac Lab

- Source: [isaac-sim/IsaacLab](https://github.com/isaac-sim/IsaacLab).
- Purpose / lab boundary: Future robot-learning experiment framework.
- Technologies: Python, PyTorch, learning methods, simulation.
- Maturity / contribution path: Active research ecosystem; reproduce a baseline before adding a task.
- Difficulty: High.
- Last push reported: 2026-10-25T08:12:33Z; license metadata: NOASSERTION.
- Limitation: Compute budget and data provenance required.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## OpenUSD

- Source: [PixarAnimationStudios/OpenUSD](https://github.com/PixarAnimationStudios/OpenUSD).
- Purpose / lab boundary: Scene interchange for future CAD-to-sim pipeline.
- Technologies: Python/C++, transforms, schemas.
- Maturity / contribution path: Established scene-description ecosystem; unit/axis round-trip examples.
- Difficulty: Medium.
- Last push reported: 2026-10-23T21:51:33Z; license metadata: NOASSERTION.
- Limitation: Does not automatically preserve identified physics across engines.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## FreeCAD

- Source: [FreeCAD/FreeCAD](https://github.com/FreeCAD/FreeCAD).
- Purpose / lab boundary: Secondary parametric CAD/CAE track.
- Technologies: Python, CAD constraints, OpenCASCADE.
- Maturity / contribution path: Established CAD application; reproduce geometry and documentation issues.
- Difficulty: Low–medium.
- Last push reported: 2026-10-26T00:25:17Z; license metadata: LGPL-2.1.
- Limitation: Generated shape must still be dimensionally validated.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## FreeCAD MCP (community candidate)

- Source: [neka-nat/freecad-mcp](https://github.com/neka-nat/freecad-mcp).
- Purpose / lab boundary: Secondary agent-assisted CAD bridge.
- Technologies: Python, FreeCAD addon, MCP.
- Maturity / contribution path: Community integration; setup examples and reproducible bug reports.
- Difficulty: Medium.
- Last push reported: 2026-10-25T01:12:47Z; license metadata: MIT.
- Limitation: Not treated as official FreeCAD capability; inspect code execution boundary.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## build123d

- Source: [gumyr/build123d](https://github.com/gumyr/build123d).
- Purpose / lab boundary: Secondary code-based parametric CAD.
- Technologies: Python, topology, OpenCASCADE.
- Maturity / contribution path: Active CAD library; documentation links and minimal geometry examples.
- Difficulty: Low for docs; medium for geometry.
- Last push reported: 2026-10-25T18:17:13Z; license metadata: Apache-2.0.
- Limitation: Exported geometry is not a calibrated mechanical model.
- Issue: see #1508 below.

## build123d MCP (community candidate)

- Source: [pzfreo/build123d-mcp](https://github.com/pzfreo/build123d-mcp).
- Purpose / lab boundary: Secondary agent-assisted model creation.
- Technologies: Python, MCP, build123d.
- Maturity / contribution path: Community integration; documented setup and model round-trip checks.
- Difficulty: Medium.
- Last push reported: 2026-10-15T20:57:23Z; license metadata: Apache-2.0.
- Limitation: Evaluate execution permissions and version compatibility before use.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## OpenModelica

- Source: [OpenModelica/OpenModelica](https://github.com/OpenModelica/OpenModelica).
- Purpose / lab boundary: Future engineering-system modeling reference.
- Technologies: Modelica, equations, numerical solvers.
- Maturity / contribution path: Established modeling ecosystem; small validated model examples.
- Difficulty: Medium–high.
- Last push reported: 2026-10-25T22:39:53Z; license metadata: NOASSERTION.
- Limitation: No co-simulation or model exchange implemented here.
- Issue: no specific beginner issue selected; inspect current issues and contribution guidelines before proposing work.

## Four concrete contribution targets

Issue states were verified open on 2026-10-26. Availability can change. No external comments, assignments or PRs were created.

| Project / issue | Difficulty [ESTIMATED] | Knowledge | First action |
|---|---|---|---|
| [build123d #1508](https://github.com/gumyr/build123d/issues/1508) — source links in docs | Low | Git, Sphinx configuration, basic Python | Build docs locally; locate theme link settings; verify generated links. No assignee at inspection; still check linked work. |
| [Gazebo docs #435](https://github.com/gazebosim/docs/issues/435) — reproduce Harmonic demo | Medium | ROS topics, bridge, launch, Gazebo | Reproduce the reported RViz/Gazebo difference on recorded versions before proposing instructions. Original report uses Ubuntu 22, not the lab's Ubuntu 24.04 baseline. |
| [ros2_control_demos #950](https://github.com/ros-controls/ros2_control_demos/issues/950) — launch cleanup | Low–medium | Python launch substitutions, colcon, tests | Review current linked PRs and one demo. Already assigned to philipchurchley; offer a bounded complementary review only after coordination. |
| [ROS docs #7217](https://github.com/ros2/ros2_documentation/issues/7217) — beginner links | Low | Git, documentation build, link checks | Recheck the four Lyrical links and redirects. Assigned to christophebedard; useful for reproduction support, not an unclaimed task. |

Start with build123d documentation if the goal is a small first contribution; keep the main lab implementation focused on ROS/Gazebo. Beginner suitability is inferred from repository skills and issue scope, not a formal assessment of the user's proficiency.
