# ADR 0001 — One actuator and a documented baseline

Date: 2026-10-26. Status: accepted for the initial documentation scope.

Problem: a broad technology portfolio can imply integrations and validation that do not exist.
Constraints: existing GAIA repositories must retain their architecture and authorship; no confirmed hardware setup, ROS installation or GPU runtime in this task.
Alternatives: full humanoid/Isaac stack now; duplicate the OP3 lab; one independent actuator experiment.
Criteria: traceability, low setup burden, measurable behavior, minimal coupling and honest evidence.
Evidence: existing OP3 simulation package and mocked LX-225 tests; mechanics identification and ROS hardware bridge remain incomplete.
Decision: document a single-actuator lab, use Jazzy/Harmonic initially and keep physical integration staged. Do not migrate existing projects.
Justification: isolates communication and state semantics before multi-joint dynamics or learning.
Consequences: no immediate Digital Twin or AI claim; each milestone requires its own implementation and evidence. No workflow added before executable artifacts justify one.
License: MIT selected for newly authored lab content only, consistent with an open-source educational lab. Linked repositories and third-party assets retain their own terms.
References: [source assessment](../references.md), [architecture](../architecture/overview.md), [roadmap](../../ROADMAP.md).
