# Claude Code & Anthropic Tooling

Date: 2026-03-06
Tags: claude-code, anthropic, mcp, remote-control

Claude Code is Anthropic's agentic coding tool living in the terminal, IDE, desktop, and browser — it reads codebases, edits files, runs commands, and handles full GitHub/GitLab workflows autonomously. Remote Control (launched late 2025) lets users issue commands from a mobile device by establishing an outbound connection from the local machine to Anthropic's API, keeping local filesystem, env vars, and MCP servers active. MCP (Model Context Protocol) support was extended to remote servers in 2025, enabling Claude Code to connect to Jira, Google Drive, Slack, and custom tooling beyond the local machine. Claude Opus 4.6 introduced a 1M-token context window (beta) and an "agent teams" mode (research preview) where multiple agents work in parallel on a codebase, each interactable via tmux. As of early 2026, Claude Code has $2.5B annualized run rate, 29M daily VS Code installs, and accounts for ~4% of all public GitHub commits.

## Why It Matters

Claude Code is the primary tool for this knowledge base and for daily agentic coding work. Understanding its Remote Control feature and MCP integration directly shapes how to structure workflows — especially for long-horizon tasks that outlast a single terminal session.

## Open Questions

- What are the practical failure modes of the "agent teams" mode in real multi-agent coding tasks — how often do sub-agents conflict or duplicate work?
- Does Remote Control persist MCP server state reliably across mobile-initiated sessions, or does context drift between handoffs?
