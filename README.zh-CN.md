# Fro Paseo Extensions

[English](README.md) | 简体中文

汇总 Fro 和 [frowang-ai](https://github.com/frowang-ai) 开发或维护的 [Paseo](https://paseo.sh/) 插件。每个插件在独立仓库中维护源码、安装说明、文档和版本记录。

## 插件目录

| 插件 | 用途 | 声明支持的 Paseo 版本 | 客户端 |
| --- | --- | --- | --- |
| [Coding Quota](https://github.com/frowang-ai/paseo-coding-quota) | 在 Paseo 额度界面及详细面板中查看 Kimi、GLM、Codex 和 Command Code 的账户用量 | `>=0.11.0` | 桌面、网页、移动端 |
| [Link Menu](https://github.com/frowang-ai/paseo-link-menu) | 右键聊天中的链接，复制实际网址或文件路径 | `>=0.10.1` | 桌面、网页 |
| [Quote](https://github.com/frowang-ai/paseo-quote) | 引用选中的聊天文字、针对段落回复，或开启侧边对话 | `>=0.10.1` | 桌面、网页 |
| [VSCode Icons](https://github.com/Rostopher/paseo-vscode-icons) | 为 Paseo 原有文件浏览器添加文件和文件夹图标 | `>=0.11.0` | 桌面、网页 |
| [Windows File Link Fix](https://github.com/frowang-ai/paseo-windows-file-links) | 修复 `/C:/project/report.html` 这类盘符前多一个斜杠的 Markdown 文件链接 | `>=0.13.2 <0.14.0` | 使用跨平台组件；移动端尚未验证 |
| [Document Viewer](https://github.com/frowang-ai/paseo-document-viewer) | 在工作区标签页中查看本地 HTML 和 PDF | `>=0.11.2 <0.13.0` | 桌面、网页 |

以上版本范围于 **2026-10-28** 根据已发布的插件清单核对，表示安装要求，不代表范围内每个 Paseo 版本都经过实测。**Document Viewer 目前不支持 Paseo 0.13 及以上版本。** 最新兼容性和限制请以各插件 README 为准。

## 安装

先在 **Settings → Plugins** 中启用插件，再到工作区所属的 daemon 主机上执行所需插件的安装命令。以下使用 Git 仓库直接安装，无需等待 Paseo 插件目录收录。

| 插件 | 运行 ID | 安装命令 |
| --- | --- | --- |
| Coding Quota | `paseo-coding-quota` | `paseo plugin add git:frowang-ai/paseo-coding-quota` |
| Link Menu | `link-menu` | `paseo plugin add git:frowang-ai/paseo-link-menu` |
| Quote | `quote` | `paseo plugin add git:frowang-ai/paseo-quote` |
| VSCode Icons | `paseo-vscode-icons` | `paseo plugin add git:Rostopher/paseo-vscode-icons` |
| Windows File Link Fix | `windows-file-links` | `paseo plugin add git:frowang-ai/paseo-windows-file-links` |
| Document Viewer（0.11.2–0.12.x） | `paseo-document-viewer` | `paseo plugin add git:frowang-ai/paseo-document-viewer` |

也可以把 `git:owner/repository` 填入插件安装表单。本仓库只是汇总目录，本身不能作为插件安装。

管理已安装的插件时使用表中的**运行 ID**，例如：

```sh
paseo plugin ls
paseo plugin update link-menu
paseo plugin disable link-menu
paseo plugin enable link-menu
```

## 配置与兼容性说明

- **Coding Quota：**在插件设置中配置账户。Codex 使用本机已有的 Codex CLI 登录凭据；其他服务使用各自的账户 API key。配置方式和凭据存储说明见插件 README。
- **Windows File Link Fix：**适用于 Windows daemon。正常的 WSL 路径，如 `/mnt/c/...` 和 `/home/...`，保持不变。插件不转换 Windows 与 WSL 路径，也不检测 daemon 的操作系统。安装需要 npm。
- **Document Viewer：**这个兼容分支面向 Paseo 0.11.2–0.12.x，daemon 主机需要 Node.js 22.22 或更新版本及 npm。安装时会准备 PDF 引擎；原生 iOS、Android 客户端不提供文档预览。
- **Link Menu、Quote 和 VSCode Icons：**依赖桌面、网页客户端的界面结构。原生移动端没有这些功能，Paseo 后续调整界面时可能需要更新插件。

各插件自己的仓库负责维护配置、平台支持、数据访问和开发说明。插件问题请到对应仓库反馈；目录缺项或信息错误请在本仓库反馈。

## 来源与致谢

本目录同时收录原创插件和维护的 fork：

- [Quote](https://github.com/frowang-ai/paseo-quote) 保留了 [keefeere/paseo-quote](https://github.com/keefeere/paseo-quote) 的实现和原作者署名。
- [Document Viewer](https://github.com/frowang-ai/paseo-document-viewer) 基于 [no-carve-only-pizza/paseo-document-viewer](https://github.com/no-carve-only-pizza/paseo-document-viewer)，增加 Paseo 0.12 兼容补丁。
- [VSCode Icons](https://github.com/Rostopher/paseo-vscode-icons) 使用 [vscode-icons](https://github.com/vscode-icons/vscode-icons) 的图标和文件关联规则；图标许可见其仓库声明。

## 维护目录

新增公开插件或调整条目时，同步更新中英文版本，并链接到插件的独立仓库。维护要求见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 许可证

本目录采用 [MIT 许可证](LICENSE)。各插件及其附带资源沿用各自许可证，收录不会改变原项目的许可。
