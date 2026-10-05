# Fro Paseo Extensions

A collection of Paseo plugins for local-first AI coding workflows.

## Plugins

| Plugin | Description | Install |
| --- | --- | --- |
| [`paseo-coding-quota`](./plugins/paseo-coding-quota) | Unified Kimi / GLM / Codex coding-plan quota dashboard | `paseo plugin install github:Rostopher/fro-paseo-extensions:plugins/paseo-coding-quota` |

More Paseo extensions will be added over time. Each plugin remains an independent package with its own manifest, tests, README, and release lifecycle.

## Development

```bash
npm install
npm run typecheck
npm test
```

## Trust and credentials

Paseo plugins are trusted, unsandboxed code. Review each plugin before installing it. Never commit API keys, OAuth tokens, local Paseo settings, or provider response dumps containing private account data.

## License

Individual plugins are licensed as documented in their own directories. Unless otherwise stated, this repository uses MIT-licensed code.
