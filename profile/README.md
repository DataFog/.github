# DataFog

**Open-source PII detection for AI agents.** Scan, redact, and guard sensitive data — locally, in milliseconds.

```python
from datafog import sanitize

sanitize("Call Sarah Chen at 415-555-0142, SSN 234-56-7890")
# → "Call [PERSON_1] at [PHONE_1], SSN [SSN_1]"
```

## Projects

### 🔒 [datafog-python](https://github.com/DataFog/datafog-python) — The core SDK
PII detection and redaction via regex + NLP cascade. One function call. <2MB core install. 190x faster than spaCy for structured PII.

`pip install datafog`

### 🔌 [datafog-mcp](https://github.com/DataFog/datafog-mcp) — MCP privacy proxy *(coming soon)*
Add PII detection to any MCP server with one config change. Wraps Postgres, filesystem, Slack, and other MCP servers — intercepts tool responses before PII enters the agent's context window.

`uvx datafog-mcp proxy --wrap <your-mcp-server>`

### 🧪 [datafog-core](https://github.com/DataFog/datafog-core) — Rust engine *(in development)*
High-performance detection core in Rust. Will power both the Python SDK (via PyO3) and native integrations.

## Use cases

**Agent guardrails** — Wrap LLM calls with `scan_prompt()` / `filter_output()` to catch PII before it enters or leaves your agent.

**MCP privacy layer** — Proxy any MCP server so tool responses are automatically scanned. Your agent reasons over `[PERSON_1]` instead of real names.

**CI/CD scanning** — `datafog scan ./data` catches PII in test fixtures, logs, and configs before they ship.

**RAG sanitization** — Scrub retrieved chunks before injecting into prompts.

## Links

🌐 [datafog.ai](https://datafog.ai) · 📦 [PyPI](https://pypi.org/project/datafog/) · 💬 [Discord](https://discord.gg/YOUR_INVITE) · 𝕏 [@datafoginc](https://twitter.com/datafoginc)
