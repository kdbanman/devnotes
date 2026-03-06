# Orchestration & Conductor Patterns for Multi-Agent Systems

Date: 2026-03-06
Tags: orchestration, multi-agent, conductor, handoff

The "conductor" pattern has formalized: a dedicated model (or layer) trained specifically to divide problems, delegate subtasks, and design communication topologies among worker LLMs — all in natural language. A 2025 paper introduced an RL-trained Conductor where a 7B model achieves state-of-the-art results on LiveCodeBench and GPQA by coordinating larger workers; allowing the conductor to select itself as a worker enables recursive topologies and dynamic test-time scaling. Handoff vs. tool-use is now a recognized design decision: use handoffs when routing is part of the workflow and a specialist should own the conversation; use agent-as-tool when a specialist should help with a bounded subtask without taking over. Enforcing structured (Pydantic/JSON) communication protocols for all handoffs is a best practice that prevents ambiguity and cycles. Benchmark: multi-agent orchestration achieved 100% actionable recommendation rate vs. 1.7% for single-agent (80× improvement) across 348 controlled trials.

## Why It Matters

This is the core architectural question for any non-trivial agentic coding workflow: who coordinates whom? The conductor pattern and the handoff/tool-use distinction are the key vocabulary for designing reliable multi-agent pipelines.

## Open Questions

- When is a trained RL conductor actually worth the overhead vs. a well-prompted orchestrator model — what task complexity threshold triggers the difference?
- How do conductor patterns interact with context compaction — does the conductor maintain its own summary of worker progress, or does it rely on shared state?
