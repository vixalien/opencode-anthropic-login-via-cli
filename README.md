# opencode-anthropic-login-via-cli

Use Anthropic models in [OpenCode](https://github.com/sst/opencode) with your **Claude Pro/Max subscription** — no API key needed.

## Auth Methods

### Auto — Claude CLI credentials

If you have [Claude CLI](https://github.com/anthropics/claude-code) installed and logged in, the plugin picks up your credentials automatically. Nothing else to do.

- macOS: reads from system Keychain
- Linux: reads from `~/.claude/.credentials.json`
- Tokens are refreshed automatically

### Browser — OAuth via claude.ai

Don't have Claude CLI? No problem. The browser method opens an OAuth flow through `claude.ai` directly. Just log in with your Claude Pro/Max account.

### API Key

You can also enter an Anthropic API key manually if you prefer.

## Install

Add to your `opencode.json`:

```json
{
  "plugin": ["opencode-anthropic-login-via-cli"]
}
```

Then open OpenCode and go to **Connect Provider > Anthropic**.

## License

MIT
