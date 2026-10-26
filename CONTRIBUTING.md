# Contributing

Start from a small issue with a reproducible question, current evidence and acceptance criteria.
Keep documentation, simulation and hardware claims separate. Use SI and record deviations such as temperature in °C.

For experiments include objective, hypothesis, setup, hardware/software, configuration, procedure, metrics, raw data, results, discussion, limitations and reproduction instructions.
Never overwrite raw data to improve results. Missing values are not zero.

No automatic hardware movement, firmware flash or production-service calls in CI. Hardware tests require an identified assembly, operator, limits and stop method.
Preserve team/upstream attribution; review licenses before importing CAD, models, data or code.

Current validation: review local Markdown links and status consistency; run git diff --check.
Future CI should test only implemented components: documentation/config validation first, Python tests when code exists, ROS builds and headless simulation when packages exist. Physical and GPU tests remain explicit separate jobs, not unconditional hosted-runner requirements.

Use small semantic commits. Explain what changed, how it was checked, and what remains untested.
