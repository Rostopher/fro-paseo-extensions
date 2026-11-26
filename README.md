# Fro Paseo Extensions

English | [简体中文](README.zh-CN.md)

A directory of [Paseo](https://paseo.sh/) plugins developed or maintained by Fro and [frowang-ai](https://github.com/frowang-ai). Each plugin has its own repository, installation, documentation, and release history.

## Plugins

| Plugin | What it does | Declared Paseo versions | Clients |
| --- | --- | --- | --- |
| [Coding Quota](https://github.com/frowang-ai/paseo-coding-quota) | Kimi, GLM, Codex, and Command Code usage in Paseo's quota UI and a detailed account dashboard | `>=0.11.0` | Desktop, web, mobile |
| [Link Menu](https://github.com/frowang-ai/paseo-link-menu) | Right-click a chat link to copy its address or reveal a local file in the desktop file manager | `>=0.10.1` | Desktop; copy also on web |
| [Quote](https://github.com/frowang-ai/paseo-quote) | Quote selected chat text, reply to a passage, or discuss it in a side chat | `>=0.10.1` | Desktop, web |
| [VSCode Icons](https://github.com/Rostopher/paseo-vscode-icons) | File and folder icons in Paseo's existing Files explorer | `>=0.11.0` | Desktop, web |
| [Windows File Link Fix](https://github.com/frowang-ai/paseo-windows-file-links) | Repair Markdown file links such as `/C:/project/report.html` and copy a corrected reply's full Markdown | `>=0.13.2` | Cross-platform components; mobile unverified |
| [Document Viewer](https://github.com/frowang-ai/paseo-document-viewer) | Open local HTML and PDF files in workspace tabs | `>=0.11.2 <0.13.0` | Desktop, web |

Versions were checked against the published manifests on **2026-11-26**. They describe installation requirements, not a guarantee that every matching Paseo release has been tested. **Document Viewer currently excludes Paseo 0.13 and later.** Consult each plugin's README for current compatibility and limitations.

## Link Menu preview

![Link Menu: Copy link address and Show in Explorer](https://raw.githubusercontent.com/frowang-ai/paseo-link-menu/main/docs/images/link-menu-en.png)

Version 0.2.2 adds local file reveal, faster menu preparation, and one shared menu across connected hosts. This is the actual plugin menu with sample chat content and a simulated desktop bridge. See the [English guide](https://github.com/frowang-ai/paseo-link-menu#preview) or [Chinese guide](https://github.com/frowang-ai/paseo-link-menu/blob/main/README.zh-CN.md) for usage and verification limits.

## Install

Enable plugins under **Settings → Plugins**, then run the command for the plugin you want on the daemon that owns your workspace. These are direct Git sources and do not require a Paseo registry listing.

| Plugin | Runtime ID | Install command |
| --- | --- | --- |
| Coding Quota | `paseo-coding-quota` | `paseo plugin add git:frowang-ai/paseo-coding-quota` |
| Link Menu | `link-menu` | `paseo plugin add git:frowang-ai/paseo-link-menu` |
| Quote | `quote` | `paseo plugin add git:frowang-ai/paseo-quote` |
| VSCode Icons | `paseo-vscode-icons` | `paseo plugin add git:Rostopher/paseo-vscode-icons` |
| Windows File Link Fix | `windows-file-links` | `paseo plugin add git:frowang-ai/paseo-windows-file-links` |
| Document Viewer (0.11.2–0.12.x) | `paseo-document-viewer` | `paseo plugin add git:frowang-ai/paseo-document-viewer` |

You can also paste a `git:owner/repository` source into the plugin installation form. This directory itself is not an installable plugin.

Use the **runtime ID** to manage an installed plugin. For example:

```sh
paseo plugin ls
paseo plugin update link-menu
paseo plugin disable link-menu
paseo plugin enable link-menu
```

## Setup and compatibility notes

- **Coding Quota:** configure the provider accounts in its settings. Codex uses existing local Codex CLI credentials; the other providers use their account API keys. See the plugin README for setup and credential storage.
- **Link Menu:** file reveal requires Paseo Desktop's file-manager bridge and a workspace on that desktop's local host. It has been exercised on Windows / Paseo 0.16.2. Browser clients keep copying; remote files, network shares, and WSL-to-Windows conversion are unsupported.
- **Windows File Link Fix:** intended for Windows-backed daemons. Completed corrected replies have a **Copy this reply** button that copies that message's full Markdown. Normal WSL paths such as `/mnt/c/...` and `/home/...` remain unchanged. It does not translate Windows paths into WSL paths or detect the daemon OS. npm is required for installation.
- **Document Viewer:** this compatibility fork targets Paseo 0.11.2–0.12.x. Its daemon needs Node.js 22.22 or later and npm. Installation prepares the PDF engine; native iOS and Android previews are not supported.
- **Link Menu, Quote, and VSCode Icons:** use desktop/web UI adapters. Native mobile clients do not receive these features, and later changes to Paseo's UI may require plugin updates.

Each plugin's own repository is the source of truth for setup, platform support, data access, and development commands. Report plugin bugs there; report missing or incorrect directory entries here.

## Sources and credits

This directory includes original plugins and maintained forks:

- [Quote](https://github.com/frowang-ai/paseo-quote) retains the implementation and attribution from [keefeere/paseo-quote](https://github.com/keefeere/paseo-quote).
- [Document Viewer](https://github.com/frowang-ai/paseo-document-viewer) is a Paseo 0.12 compatibility fork of [no-carve-only-pizza/paseo-document-viewer](https://github.com/no-carve-only-pizza/paseo-document-viewer).
- [VSCode Icons](https://github.com/Rostopher/paseo-vscode-icons) uses artwork and associations from [vscode-icons](https://github.com/vscode-icons/vscode-icons); see its notices for the artwork licenses.

## Maintaining this directory

Update both language versions when adding a public plugin or changing an entry. Keep links pointed at the independent repositories. See [CONTRIBUTING.md](CONTRIBUTING.md) for the entry checklist.

## License

This directory is [MIT licensed](LICENSE). Each linked plugin and its bundled assets retain their own licenses; listing a project here does not change them.
