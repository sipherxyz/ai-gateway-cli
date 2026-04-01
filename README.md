# AI Gateway CLI

`ai-gateway` is a cross-platform launcher for Claude Code, Codex, Pi, and arbitrary programs that automatically configures the right AI Gateway runtime for each tool.

## Install / Update

macOS / Linux:

```bash
curl -fsSL https://ai-gateway.atherlabs.com/install.sh | bash
```

Windows (PowerShell):

```powershell
powershell -c "irm https://ai-gateway.atherlabs.com/install.ps1 | iex"
```

## Login

```bash
ai-gateway login
```

### Use with coding CLIs

```bash
ai-gateway claude
ai-gateway codex
ai-gateway droid
ai-gateway pi
```

You can pass through any args after the command, for example:

```bash
ai-gateway claude --dangerously-skip-permissions
ai-gateway codex --dangerously-bypass-approvals-and-sandbox
```

### Run arbitrary program:

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

List available credentials:

```bash
ai-gateway credentials list
ai-gateway credentials simulate --model <model-id>
```
