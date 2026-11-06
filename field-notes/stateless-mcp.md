# MCP deleted the session: where does state live now? | Aicent Stack

18 Oct 2026 · [Read the full article](https://blog.aicent.com/stateless-mcp/) · [Chinese version](https://blog.aicent.com/zh/stateless-mcp/)

The Model Context Protocol's 2026-07-28 revision removes protocol-level sessions, the initialize handshake and the Mcp-Session-Id header. Every request now carries its own version, capabilities and self-asserted identity in _meta; cross-call state moves into server-minted handles. A deep dive into where state lives after the protocol's largest structural change &mdash; and the two rows still missing from the table.
