<p align="center">
  <a href="https://datafog.ai"><img src="https://raw.githubusercontent.com/DataFog/datafog-mcp/main/docs/assets/datafog-icon.svg" width="72" height="72" alt="DataFog"></a>
</p>

<h1 align="center">DataFog</h1>

<p align="center"><strong>Keep sensitive data out of AI workflows.</strong></p>

<p align="center">
  <a href="https://datafog.ai">Website</a> ·
  <a href="https://docs.datafog.ai">Documentation</a> ·
  <a href="https://github.com/DataFog/datafog-mcp">MCP server</a> ·
  <a href="https://github.com/DataFog/datafog-core">Core engine</a>
</p>

DataFog builds open-source tools for local PII detection and privacy transformations.

- **Use it with Claude Code:** [DataFog MCP](https://github.com/DataFog/datafog-mcp)
  scans local files and creates redacted, masked, or cleaned copies. The original
  stays unchanged. Tool responses report counts, locations, and copy paths without
  returning file contents or matched values.
- **Build it into your application:** [DataFog Core](https://github.com/DataFog/datafog-core)
  provides the Rust engine and SDKs for Python, Node.js, and browsers.

## Start with a customer CSV

Have a customer export with emails and phone numbers? Ask Claude Code to check it,
then create a copy with those fields redacted before analysis. Detection and
transformation run locally.

![Claude Code creates a redacted customer CSV with DataFog MCP.](https://raw.githubusercontent.com/DataFog/datafog-mcp/main/docs/demo/transform.gif)

**[Install DataFog MCP](https://github.com/DataFog/datafog-mcp#quickstart) ·
[Try the sample CSV](https://github.com/DataFog/datafog-mcp/blob/main/docs/demo/customers.csv) ·
[Privacy boundaries](https://github.com/DataFog/datafog-mcp/blob/main/docs/privacy.md)**

## Choose your starting point

| Repository | Role |
| --- | --- |
| **[datafog-mcp](https://github.com/DataFog/datafog-mcp)** | Local file scanning and redacted copies for AI agents. Stable v1.0.0, tested with Claude Code. |
| **[datafog-core](https://github.com/DataFog/datafog-core)** | Recommended starting point for new applications. Shared detection and transformation engine, with Rust, Python, Node.js, and browser SDKs. |
| [datafog-python](https://github.com/DataFog/datafog-python) | Established Python package, including the Claude Code hook and LiteLLM guardrail adapter. Moving to Core? Follow the [migration guide](https://docs.datafog.ai/guides/migrating-from-datafog-python). |
| [datafog-claude-plugin](https://github.com/DataFog/datafog-claude-plugin) | Claude Code integration, with its own setup and release path. |
| [fogclaw](https://github.com/DataFog/fogclaw) | OpenClaw integration for PII detection and redaction. |

Core is a separate package and API from the established `datafog` Python
library. Existing integrations have their own capabilities and release paths;
Core adoption is a separate next step.

## Build with Core

- **Detect:** scan text and parsed JSON records, including supported person-name
  fields, with local built-in detectors.
- **Transform:** redact, mask, remove, pseudonymize, or tokenize selected values.
  Select entity types, apply per-entity rules, and exempt approved values.
- **Restore:** restore provider-issued tokens under an exact request scope.
  Your provider owns storage and authorization.

Browser SDKs support detection and stateless transformations. Provider-backed
pseudonymization, tokenization, and restoration are available in Rust, Python,
and Node.js. See the [SDK installation guide](https://docs.datafog.ai/get-started/installation)
and [transformation guide](https://docs.datafog.ai/concepts/privacy-transformations).

Core supplies detection and transformation. Your application or integration
chooses where to invoke it and how to enforce policy.

## Where we’re going

One shared privacy engine across more application, agent, and gateway workflows.
Core owns detection and transformation; integrations connect that behavior to
the places data moves, including workflow-specific interception and enforcement.

Follow the [Core roadmap](https://github.com/DataFog/datafog-core/blob/main/docs/privacy-operations-roadmap.md)
for implementation status and the [Core releases](https://github.com/DataFog/datafog-core/releases)
for shipped capabilities.

## Links

[Website](https://datafog.ai) · [Documentation](https://docs.datafog.ai) ·
[Installation](https://docs.datafog.ai/get-started/installation) ·
[Contributing](https://docs.datafog.ai/development) ·
[Discord](https://discord.gg/bzDth394R4)
