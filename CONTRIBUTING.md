# Contributing

This repository is a directory of independently maintained Paseo plugins. Plugin source, dependencies, releases, and tests live in each plugin's own repository.

## Add or update an entry

Update both `README.md` and `README.zh-CN.md` in the same change. Include:

- The display name, a public repository link, and a short description of what the plugin does.
- The runtime ID and a direct installation command: `paseo plugin add git:owner/repository`.
- The Paseo version range from the published `paseo-plugin.json` and supported clients from its documentation.
- Setup requirements or limitations that affect whether someone can use it.
- Upstream attribution when the repository is a fork or bundles third-party assets.

Check the published repository and manifest rather than relying on a local checkout. Keep declared compatibility distinct from versions that have actually been tested. Update the verification date when rechecking the catalog.

## Review

Open the repository and documentation links, verify the install sources and runtime IDs, and compare both language versions. Markdown-only changes do not require an npm install, a build, or a test suite.

Keep descriptions factual. Do not copy plugin source or dependencies into this repository, list unpublished local experiments as installable plugins, or include credentials and local account data.
