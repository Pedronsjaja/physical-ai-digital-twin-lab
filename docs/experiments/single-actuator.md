# EXP-001 — Single-actuator state comparison

Status: **Planned**. Results: **NOT_MEASURED**. Hardware connected: **NOT_VERIFIED**.

## Objective
Establish a reproducible position-state interface, then characterize physical/virtual synchronization for one identified actuator.

## Hypothesis
Increasing communication delay or sampling interval increases the age of available state and may increase aligned trajectory error. This is a hypothesis, not an observed result.

## Architecture
LX-225 → BusLinker → Python read-only adapter → ROS 2/RMW/DDS → virtual joint/Gazebo, with raw recording at source and sink. First execute a virtual-only baseline; never describe its generated samples as physical measurements.

## Hardware
Candidate LX-225 and BusLinker revision: UNKNOWN. Supply, serial interface, fixture, external angular reference, load, zero/sign, bounds and stop method: TODO: dado não disponível. Consult the bench's datasheets before wiring or movement.

## Software
Proposed Ubuntu 24.04/Jazzy/Harmonic. Record OS/kernel, CPU/RAM, native/VM, exact commits, dependencies, RMW version, QoS, solver/step size, launch arguments and runtime configuration.

## Configuration
Predeclare trajectory, angle range, frequency, duration, warm-up, repeats, load, sample rate, stale threshold, alignment policy and acceptance tolerance. Physical values remain UNKNOWN until justified. Virtual toy geometry must be marked ASSUMED and never called an identified LX-225 model.

## Procedure
1. Start isolated virtual actuator; check joint axis, radians, limits and clock.
2. Command a small predefined virtual trajectory; record observed feedback independently of the command.
3. Verify rejection of invalid/stale samples and failure when feedback stops.
4. When hardware is confirmed, acquire read-only feedback with one serial owner.
5. Identify zero/sign/transmission and timestamp boundaries; record reference-instrument uncertainty.
6. After separate safety acceptance, perform bounded trajectories in both directions.
7. Repeat controlled communication conditions in randomized order; preserve failures.
8. Hash raw files, align valid samples using the declared method and publish derived analysis separately.

## Metrics
For matched time t, absolute state error e(t) = |theta_physical(t) − theta_virtual(t)| [rad].
RMSE = sqrt(sum((theta_physical_i − theta_virtual_i)^2)/N) [rad].
Record N, excluded samples/reasons and overlap interval. No RMSE for N=0. Interpolation, if used, must state gap limits; do not extrapolate through outages.
Compare aligned and unaligned error separately: compensation can hide operational delay.

A virtual joint forced to copy physical samples measures mirroring/transport consistency, not model fidelity. To evaluate dynamics, let the virtual model evolve independently under a common input.
Servo feedback is not an external ground-truth instrument.

## Raw data
Future runs use data/raw/REAL/<run_id> and data/raw/SIMULATED/<run_id>, with manifest, configuration, source/sink logs and checksums. Keep CALCULATED/ESTIMATED channels explicit. Derived outputs belong under data/derived/<run_id>, linked to raw hashes. No datasets are included now.

## Results
NOT_MEASURED. No plots, benchmark values or pass/fail claims exist.

## Discussion
To be completed from data, including negative results, dropped samples and clock uncertainty.

## Limitations
Serial host timestamps approximate reply availability; acquisition time inside the servo is unknown. Sequential channel polling, quantization, load, friction, solver error and clock mapping can affect conclusions.

## Reproduction instructions
Runtime commands will be added with the executable package. At present only the protocol can be reviewed; there is no command that runs EXP-001.
The future report must include exact setup/launch commands, environment lock, raw data and analysis command.

## Learning
Study units/reference frames, ROS clocks, QoS compatibility and measurement uncertainty. Exercise: explain why a mirror can have near-zero aligned RMSE while still being too delayed for control.
