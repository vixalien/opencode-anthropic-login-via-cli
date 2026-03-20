# opencode-anthropic-login-via-cli

[OpenCode](https://github.com/sst/opencode) plugin that lets you use Anthropic models with your Claude Pro/Max subscription. No API key required.

## What It Does

- **Binary introspection**: Reads the Claude CLI binary to pull current beta headers, OAuth scopes, and version info. Stays in sync with Anthropic's API automatically instead of relying on hardcoded values.
- **Auto login**: If you have Claude CLI installed and logged in, the plugin picks up your credentials from the system keychain (macOS) or `~/.claude/.credentials.json` (Linux). No extra steps.
- **Browser login**: Opens an OAuth flow through `claude.ai` for those who don't have the CLI. Log in, paste the code, done.
- **Token refresh**: Handles expired tokens in the background. Tries the standard refresh flow first, falls back to reading fresh credentials from the CLI if needed.
- **Request patching**: Adds the right auth headers, beta flags, and tool name prefixes so OpenCode talks to Anthropic's API the same way Claude Code does.

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
