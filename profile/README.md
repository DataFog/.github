# DataFog

**Local PII protection for AI applications.**

DataFog helps developers detect sensitive information in text and structured
records, then choose how to protect it before passing it to a model, a log,
or another system.

**Start with [DataFog Core](https://github.com/DataFog/datafog-core)** — our Rust
engine with SDKs for Python, Node.js, and browsers. Redact, mask, or remove
sensitive values across runtimes. Use application-supplied providers for
pseudonymization and reversible tokenization in Rust, Python, and Node.js.

**[Get started](https://docs.datafog.ai/get-started/quickstart) ·
[Documentation](https://docs.datafog.ai) ·
[Try the demo](https://datafog.ai/#demo)**

## Choose your starting point

| Repository | Role |
| --- | --- |
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
for implementation status and the [release notes](https://docs.datafog.ai/releases/0-3-0)
for shipped capabilities.

## Links

[Website](https://datafog.ai) · [Documentation](https://docs.datafog.ai) ·
[Installation](https://docs.datafog.ai/get-started/installation) ·
[Contributing](https://docs.datafog.ai/development) ·
[Discord](https://discord.gg/bzDth394R4)
