# opencode-anthropic-login-via-cli

Use Anthropic models in [OpenCode](https://github.com/sst/opencode) with your Claude Pro/Max subscription — no API key needed.

This plugin reads your Claude CLI OAuth token and injects it into OpenCode automatically. If the token is expired, it runs `claude` CLI to refresh it.

## Prerequisites

- [OpenCode](https://github.com/sst/opencode) installed
- [Claude CLI](https://github.com/anthropics/claude-code) installed and logged in (`claude` command available)
- Active Claude Pro or Max subscription

## Install

```bash
# in your project directory
bun add opencode-anthropic-login-via-cli
```

Add to your `opencode.json`:

```json
{
  "plugin": {
    "anthropic-login": {
      "module": "opencode-anthropic-login-via-cli"
    }
  }
}
```

Or install from git:

```json
{
  "plugin": {
    "anthropic-login": {
      "module": "github:cemalturkcan/opencode-anthropic-login-via-cli"
    }
  }
}
```

## How it works

1. On session start, reads `~/.claude/.credentials.json`
2. If token is expired or about to expire, runs `claude -p . --model claude-haiku-4-5-20250514` to trigger a refresh
3. Injects the fresh token as `x-api-key` header before every Anthropic API call
4. Proactively refreshes in the background when token is within 30 minutes of expiry

No manual token management needed. Just log into Claude CLI once and use Anthropic models in OpenCode.

## License

MIT
