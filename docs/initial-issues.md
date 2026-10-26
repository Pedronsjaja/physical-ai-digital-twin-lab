# Initial issue drafts

These eight items were published as [Issues #1–#8](https://github.com/Pedronsjaja/physical-ai-digital-twin-lab/issues) on 2026-10-26. Their numbers below match GitHub. Topic labels were created and applied; good first issue was created but not assigned before task-scope review. Hardware integration is not automatically beginner-safe.

## 1. Define Digital Twin Lab architecture

Suggested labels: documentation, digital-twin.

Scope: Review the documented boundaries and resolve state ownership, clocks and failure handling.

Acceptance criteria: A reviewed diagram; clear model/shadow/twin claim criteria; unresolved decisions logged.

Dependencies: None; architecture draft already exists.

Status: Planned; do not close from documentation presence alone.

## 2. Create ROS 2 workspace structure

Suggested labels: ros2, documentation.

Scope: Create the first real package in ros2_ws/src; do not add empty package directories.

Acceptance criteria: Clean colcon build/test on pinned Jazzy environment; package install exposes launch; versions logged.

Dependencies: Architecture review.

Status: Planned; do not close from documentation presence alone.

## 3. Create minimal Gazebo actuator simulation

Suggested labels: simulation, ros2.

Scope: Implement one fixed-base revolute joint with documented synthetic parameters.

Acceptance criteria: Command changes independently observed SIMULATED feedback; absent/stale feedback fails; headless run and logs.

Dependencies: Workspace and state-contract review; first implementation slice.

Status: Planned; do not close from documentation presence alone.

## 4. Define physical/virtual state message format

Suggested labels: digital-twin, ros2.

Scope: Resolve the proposed JointState plus provenance approach, units, source identity and clock mapping.

Acceptance criteria: Document schema, missing values, sequence reset, calibration and channel quality; examples labeled synthetic.

Dependencies: Architecture draft.

Status: Planned; do not close from documentation presence alone.

## 5. Design latency and jitter benchmark

Suggested labels: research.

Scope: Turn the methodology into a precise future runner specification.

Acceptance criteria: Named timestamps, clock uncertainty, N requirements, warm-up/repeats, percentiles and app-vs-network loss definitions; no invented results.

Dependencies: State contract.

Status: Planned; do not close from documentation presence alone.

## 6. Evaluate Fast DDS vs Cyclone DDS test methodology

Suggested labels: research, ros2.

Scope: Specify a fair RMW comparison on a fixed workload and actual transport.

Acceptance criteria: Version/QoS/config matrix; randomized trials; shared-memory/UDP distinction; reproducibility plan.

Dependencies: Benchmark design.

Status: Planned; do not close from documentation presence alone.

## 7. Design LX-225 ROS 2 integration

Suggested labels: hardware, ros2.

Scope: Specify read-only adapter around existing driver before any motion interface.

Acceptance criteria: One serial owner; degree-to-radian calibration; per-channel validity; host timing limits; failure behavior documented.

Dependencies: State contract; confirmed hardware details remain UNKNOWN.

Status: Planned; do not close from documentation presence alone.

## 8. Investigate ros2_control hardware interface for LX-225

Suggested labels: hardware, research.

Scope: Evaluate C++ plugin versus process bridge using measured future requirements.

Acceptance criteria: ADR covering lifecycle, blocking IO, bounded read/write and fault handling; no unverified real-time claim.

Dependencies: Read-only integration design; no hardware actuation in this issue.

Status: Planned; do not close from documentation presence alone.
