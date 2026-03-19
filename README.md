# AI Gateway CLI

`ai-gateway` is a cross-platform launcher for Claude Code, Codex, Pi, and arbitrary programs that automatically configures the correct gateway environment variables.

## Install / Update

macOS / Linux:

```bash
curl -fsSL https://ai-gateway.atherlabs.com/install.sh | bash
```

Windows (PowerShell):

```powershell
irm https://ai-gateway.atherlabs.com/install.ps1 | iex
```

## Login

```bash
ai-gateway login
```

For local development:

```bash
ai-gateway --dev login
```

## Run

Claude Code:

```bash
ai-gateway claude
ai-gateway claude --cred <id> --group <group-id>
```

Codex:

```bash
ai-gateway codex
ai-gateway codex --cred <id> --group <group-id>
```

Pi:

```bash
ai-gateway pi
ai-gateway pi --cred <id> --group <group-id> [args...]
```

`ai-gateway pi` injects `ANTHROPIC_*`, `AZURE_OPENAI_*`, and `GEMINI_*` gateway env vars.

Arbitrary program:

```bash
ai-gateway run <program> [args...]
ai-gateway run <program> [args...] --expose <all|claude|openai|azure-openai|gemini>[,...]
ai-gateway run <program> [args...] --cred <id> --group <group-id>
```

`ai-gateway run` injects `ANTHROPIC_*`, `OPENAI_*`, `AZURE_OPENAI_*`, and `GEMINI_*` env vars by default.

List models grouped by provider:

```bash
ai-gateway models
```

You can pass through any args after the command, for example:

```bash
ai-gateway claude --help
```
