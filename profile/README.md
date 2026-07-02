# DataFog

**The offline PII firewall for AI agents and LLM apps.**

Agents move sensitive data through prompts, tool calls, files, and gateways
all day. DataFog catches PII at the boundary — before it leaves the machine —
running a simple loop on every payload:

- **detect** sensitive entities locally (regex-first, microseconds per scan,
  zero network calls, one dependency)
- **decide** what policy says (allow, redact, block)
- **enforce** before the action executes

No sidecar services, no cloud API that sees your data. The only PII layer in
the agent ecosystem where analysis never leaves your machine.

## Get protected in 60 seconds

**Python:**

```python
# pip install datafog
import datafog
print(datafog.redact("email me at jane.doe@example.com").redacted_text)
# email me at [EMAIL_1]
```

**Claude Code** — firewall every agent tool call:

```
/plugin marketplace add DataFog/datafog-claude-plugin
/plugin install datafog@datafog
```

**LiteLLM gateway** — redact requests to any provider (~31µs per request):

```yaml
guardrails:
  - guardrail_name: "datafog-pii"
    litellm_params:
      guardrail: datafog.integrations.litellm_guardrail.DataFogGuardrail
      mode: "pre_call"
      default_on: true
```

## Projects

| Project | What it is |
|---|---|
| [datafog-python](https://github.com/DataFog/datafog-python) | The engine: PII detection, redaction, and agent guardrails. Ships the Claude Code hook and LiteLLM guardrail. |
| [datafog-claude-plugin](https://github.com/DataFog/datafog-claude-plugin) | One-command Claude Code plugin wrapping the hook. |
| [fogclaw](https://github.com/DataFog/fogclaw) | OpenClaw plugin for PII detection and redaction. |
| [datafog](https://github.com/DataFog/datafog) | Runtime policy engine and policy gate: scan/decide/transform APIs with auditable decision receipts. |
| [datafog-mcp](https://github.com/DataFog/datafog-mcp) | MCP privacy proxy — govern tool responses before they reach model context. *(coming soon)* |

## Honest scope

DataFog is a seatbelt against accidental leakage — the pasted stack trace
that ends up in a committed test fixture, the customer record that drifts
into a GitHub issue. It is not armor against deliberate exfiltration or
prompt injection, and inbound PII you hand an agent directly should be
redacted before sharing (`datafog` CLI does that too). We document the
limitations as carefully as the features.

## Links

[datafog.ai](https://datafog.ai) · [PyPI](https://pypi.org/project/datafog/) · [Discord](https://discord.gg/bzDth394R4) · [Changelog](https://github.com/DataFog/datafog-python/blob/main/CHANGELOG.MD)
