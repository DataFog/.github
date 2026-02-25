# DataFog

**Runtime data governance for AI agents and developer tooling.**

DataFog runs a policy-enforced loop on sensitive payloads as they move through commands, files, and tool calls:

- **detect** sensitive entities
- **decide** what policy says (`allow`, `transform`, `allow_with_redaction`, `deny`)
- **enforce** before the action executes

It is the data firewall for your local developer + agent workflows.

```bash
# Drop DataFog into your PATH with a policy gate wrapper
datafog-shim hooks install --target /usr/bin/git git
```

```python
from datafog import scan
scan("Call Sarah Chen at 415-555-0142, SSN 234-56-7890")
# -> [{"entity_type": "NAME", "value": "Sarah Chen", ...}, ...]
```

## Projects

### 🔌 [datafog](https://github.com/DataFog/datafog) — Runtime policy engine + policy gate
Process-boundary enforcement with scan/decide/transform APIs, receipts, and adapter-aware policy matching.

### 🐍 [datafog-python](https://github.com/DataFog/datafog-python) — Python SDK
SDK + CLI bindings for integrating DataFog policies into agent and app pipelines.

### 🧩 [datafog-mcp](https://github.com/DataFog/datafog-mcp) — MCP privacy + policy proxy *(coming soon)*
Integrate policy-aware interception for MCP tool responses, so sensitive values are governed before they reach context.

## Use cases

- **Developer- and AI-tool guardrails** — enforce policy before shell/file/API actions execute.
- **Runtime DLP for agents** — treat policy as code, with decision receipts and auditable logs.
- **CI/CD and compliance checks** — scan artifacts and enforce data handling controls in workflows.

## Links

🌐 [datafog.ai](https://datafog.ai) · 📦 [PyPI](https://pypi.org/project/datafog/) · 𝕏 [@datafoginc](https://twitter.com/datafoginc)
