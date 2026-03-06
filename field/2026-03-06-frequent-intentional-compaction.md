# Frequent Intentional Compaction — Managing Agent Context at Scale

Date: 2026-03-06
Tags: context-management, compaction, summarization, long-horizon-agents

"Context rot" is the observed degradation in LLM performance as the context window fills, even well below the technical token limit (e.g., performance degrades around 256k tokens in a 1M-token window). Three main strategies have emerged: LLM summarization (lossy, can hallucinate or lose critical specifics like file paths and error messages), context compaction (strips redundant info that exists in the environment, reversible via tool calls), and observation masking (replaces old tool outputs with placeholders while keeping tool calls visible). The recommended priority order is raw > compaction > summarization — only summarize when compaction isn't enough. ACON research shows adaptive context optimization reduces peak token usage 26–54% while maintaining task performance. ReSum (periodic summarization for web agents) shows a 4.5% absolute improvement over ReAct baseline. Structured summarization with dedicated sections (file paths, decisions, errors) outperforms freeform summarization by forcing preservation of specific categories.

## Why It Matters

Long-horizon agentic coding tasks — debugging, large refactors, multi-session projects — live or die by context management. Knowing when to compact, when to summarize, and how to structure summaries to avoid losing critical specifics (exact error messages, file paths, prior decisions) is a core operational skill for any agent workflow.

## Open Questions

- Is there a reliable heuristic for detecting the onset of context rot without waiting for task failure — e.g., a measurable signal like repetition rate or confidence scores on tool selection?
- How does Claude Code's built-in compaction (if any) interact with manually structured notes passed via system prompt — does it respect user-defined structure or flatten everything?
