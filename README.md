# AI Gateway CLI

`ai-gateway` is a cross-platform launcher for Claude Code and Codex that automatically configures the correct gateway environment variables.

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
```

Codex:

```bash
ai-gateway codex
```

You can pass through any args after the command, for example:

```bash
ai-gateway claude --help
```

