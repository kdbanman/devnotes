# Reflection and Self-Correction Loops in Agent Systems

Date: 2026-03-06
Tags: reflection, self-correction, error-recovery, agent-robustness

Self-correction in LLMs spans intrinsic (no external feedback) and extrinsic (with external signals like test results or critic models) approaches — research consistently finds intrinsic correction unreliable or even harmful without external grounding. The foundational pattern is Reflexion: the agent inspects its full trajectory, generates a self-critique, and restarts generation with that critique in context. PALADIN (ICLR 2026) goes further by training directly on failure-rich trajectories with explicit diagnosis and replanning steps across multiple tool calls — moving from reactive post-hoc correction to proactive trajectory-level robustness. MCP-SIM formalizes the cycle as plan–act–reflect–revise, which maps well onto coding agents that write code, run tests, observe failures, and revise. The key practical limit: without external feedback (test output, linter results, type errors), self-correction often degrades performance rather than improving it.

## Why It Matters

Every coding agent loop is implicitly a reflection loop — write code, run tests, observe, revise. Understanding what makes these loops reliable (external signals, structured critique, trajectory-level training) vs. fragile (pure self-evaluation) directly informs how to design agent tasks and what guardrails to build in.

## Open Questions

- Is there a "Ralph loop" pattern documented specifically for coding agents where the agent gets stuck in a revision cycle without converging — and what are the canonical exit conditions?
- How does PALADIN's failure-rich training interact with general capability — does training on error trajectories hurt performance on tasks where the agent would have succeeded without correction?
