# SDLC-Thinking as a First-Class Agentic Skill

Date: 2026-03-06
Tags: sdlc, spec-driven-development, agentic-engineering, planning

Agentic software development (ASD) treats planning, spec, implementation, testing, and review as stages an AI agent owns end-to-end, not just assists with. GitHub released the open-source Spec Kit in 2025, making specifications a first-class artifact: specs drive implementation checklists and task breakdowns, steering an orchestrator toward the end goal rather than leaving intent implicit. Multi-agent architectures map naturally onto SDLC stages — an Orchestrator agent handles planning and coordination while Worker agents handle file analysis, code generation, test writing, and documentation in parallel. AI-assisted code review is measurably effective: Qodo's 2025 report found AI code review raised quality improvements from 55% to 81%; Atlassian's 2026 study found 38.7% of AI review comments led to additional code fixes. Security risk scales with autonomy — an agent writing 1,000 PRs/week at 1% vulnerability rate introduces 10 new vulnerabilities weekly.

## Why It Matters

The shift from "agent writes code" to "agent manages a full SDLC" is the core transition happening in 2026. Knowing how to structure specs, task breakdowns, and review gates directly determines whether an agentic coding workflow produces reliable output or accumulates debt.

## Open Questions

- How does Spec Kit handle spec drift — when the codebase evolves and the spec becomes stale, does the agent detect and flag the mismatch, or does it silently diverge?
- At what autonomy level does the security vulnerability accumulation rate outpace human review capacity — and what monitoring patterns catch this before it compounds?
