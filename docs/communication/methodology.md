# Communication experiments — design only

No benchmark runner or performance data exists.

## Measurement boundaries

| Metric | Definition / unit | Caveat |
|---|---|---|
| Application latency | receive time − publish time [s], same clock domain | Includes scheduling/serialization; not pure wire delay |
| Acquisition-to-receipt age | sink receipt − source observation [s] | Host timestamp after serial reply does not expose sensor acquisition time |
| Jitter | sample standard deviation of valid latency [s], N≥2 | Also report inter-arrival variation separately; do not mix definitions |
| Update rate | (N−1)/(last receive−first receive) [Hz], positive duration | Use unique samples; report configured and observed rates |
| Application sample loss | (published unique−received unique)/published unique over matched run/window | Account for warm-up, drain, duplicates, reordering and late delivery; not network packet loss |
| Network packet loss | missing wire-level packets / transmitted packets | Requires separate network instrumentation; DDS retries/fragmentation prevent equivalence |
| Bandwidth | bytes per second at a named boundary [B/s] | Payload bytes differ from wire bytes |
| CPU / RAM | process CPU with normalization and RSS [%, bytes] | Identify core count, sampling tool and interval |
| Synchronization error | aligned absolute error and RMSE [rad] | Record time alignment and measurement uncertainty |

## Controlled DDS comparison

Compare rmw_fastrtps_cpp and rmw_cyclonedds_cpp with fixed ROS version, message type/payload, publisher/subscriber count, rate, topology and machine load. Record vendor version, discovery settings and actual transport (shared memory versus UDP), not just RMW name.

Test reliability (reliable/best effort), history/depth, durability, deadline and lifespan using explicitly compatible publisher/subscriber settings. Log offered/requested profiles and incompatible-QoS events. Reliable delivery does not guarantee a latency deadline.

Start same-host and isolated domain. Then separate-host wired tests with clock synchronization evidence. Any traffic impairment belongs in an isolated test network; do not change production networking. Randomize trial order, specify repeats/warm-up/duration before collection, and preserve per-run results, percentiles and failure rate rather than only pooled averages.

Fast DDS versus Cyclone DDS has no declared winner. Results apply only to the recorded workload and environment. Middleware-only timing must be kept separate from LX-225 acquisition and Gazebo solver timing.
