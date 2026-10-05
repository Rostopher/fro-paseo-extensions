# Contributing

Each plugin lives under `plugins/<plugin-id>/` and must be independently installable by Paseo.

Before submitting changes:

```bash
npm install
npm run typecheck
npm test
```

Do not include provider credentials, OAuth tokens, local daemon state, or private response dumps. Keep plugin-specific documentation and tests inside the plugin directory.
