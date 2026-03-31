# AI Gateway CLI

`ai-gateway` is a cross-platform launcher for Claude Code, Codex, Pi, and arbitrary programs that automatically configures the right AI Gateway runtime for each tool.

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

Droid:

```bash
ai-gateway droid
ai-gateway droid --cred <id> --group <group-id> [args...]
ai-gateway droid exec --model gpt-5.4 "fix the failing test"
```

`ai-gateway droid` writes a managed Droid overlay to `~/.factory/settings.ai-gateway.json`, points `droid --settings` at that file, syncs AI Gateway OpenAI, Anthropic, and OpenAI-compat models into `customModels`, maps OpenAI-compat entries to Droid's `generic-chat-completion-api`, and injects `_AI_GATEWAY_API_KEY` at launch time.

Pi:

```bash
ai-gateway pi
ai-gateway pi --cred <id> --group <group-id> [args...]
```

`ai-gateway pi` writes a managed Pi extension to `~/.pi/ai-gateway/extension.ts`, loads it via `pi -e`, registers `ai-gateway-openai`, `ai-gateway-openai-compat`, and `ai-gateway-anthropic` from the live AI Gateway `/v1/models` list, and injects only `_AI_GATEWAY_API_KEY` at launch time.

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
