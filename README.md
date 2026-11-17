<div align="center">

# linuxdo-idea-ui-Bak

linuxdo-idea-ui 上游仓库的源码镜像

[![Upstream](https://img.shields.io/badge/upstream-czm15053%2Flinuxdo--idea--ui-181717?logo=github&logoColor=white)](https://github.com/czm15053/linuxdo-idea-ui)
[![Branch](https://img.shields.io/badge/branch-main-2ea44f?logo=git&logoColor=white)](https://github.com/czm15053/linuxdo-idea-ui/tree/main)
[![Sync](https://img.shields.io/github/actions/workflow/status/hopol/linuxdo-idea-ui-Bak/sync.yml?label=sync&logo=githubactions&logoColor=white)](https://github.com/hopol/linuxdo-idea-ui-Bak/actions/workflows/sync.yml)
[![Mirror License](https://img.shields.io/badge/mirror-MIT-blue.svg)](LICENSE)

[上游仓库](https://github.com/czm15053/linuxdo-idea-ui) · [Actions](https://github.com/hopol/linuxdo-idea-ui-Bak/actions)

</div>

---

## 📌 说明

本仓库用于镜像 [`czm15053/linuxdo-idea-ui`](https://github.com/czm15053/linuxdo-idea-ui) 的源码。

- 源码来自上游 `main` 分支，导出到 `upstream/`。

- 本仓库不修改上游源码，不提供上游项目的官方支持。

> [!NOTE]
> 上游项目描述：给 linux.do 换装的油猴脚本合集：JetBrains/Darcula IDE 风格、飞书 IM、钉钉 IM 三种外观，仅换皮不碰数据。功能说明、安装方式、更新内容和使用要求请以上游仓库为准。

## 📁 镜像范围

| 内容 | 位置 | 说明 |
|---|---|---|
| 上游源码 | `upstream/` | 通过 `git archive` 从上游 `main` 分支导出。 |
| 同步信息 | `upstream/.sync-info` | 记录上游提交、同步时间、分支和版本或来源引用。 |
| 源码标签 | `mirror-source-…` | 对应一次源码同步。 |

## 🔄 自动同步

```mermaid
flowchart LR
    A["上游仓库<br>czm15053/linuxdo-idea-ui"] --> B["sync.yml<br>检查 main 分支"]
    B --> C{"上游提交是否变化"}
    C -->|"否"| D["结束"]
    C -->|"是"| E["导出源码到 upstream/"]
    E --> F["写入 .sync-info"]
    F --> G["提交并创建源码标签"]
```

> [!IMPORTANT]
> GitHub Actions 中的定时任务使用 UTC 时间。cron 表达式的日期字段为 `*/5`，通常在每月 1、6、11、16、21、26、31 日运行，并不等同于严格每 5 天运行一次。

## 🧾 同步信息

```ini
commit=0123456789abcdef...
timestamp=2026-08-07T00:00:00Z
upstream_url=https://github.com/czm15053/linuxdo-idea-ui
upstream_branch=main
version=1.0.0
```

`version`：从上游 `doc-select.user.js` 的用户脚本元数据 `@version` 读取。

同步脚本会在删除 `upstream/` 前读取已提交的 `.sync-info`。只有上游提交变化时，才会更新源码、创建提交和标签。

## 💻 本地同步源码

`sync.sh` 用于本地手动同步源码。它需要 Git、Bash 环境（Linux、macOS、WSL 或 Git Bash）和对镜像仓库的推送权限。

```bash
git clone https://github.com/hopol/linuxdo-idea-ui-Bak.git
cd linuxdo-idea-ui-Bak
chmod +x sync.sh
./sync.sh
```

## 🛠️ 维护常用命令

```bash
# 查看当前镜像对应的上游提交
git show HEAD:upstream/.sync-info

# 列出镜像标签
git tag -l 'mirror-*'

# 手动拉取上游分支
git fetch upstream main --tags
```

## ⚖️ 许可证

- 本仓库的同步脚本、GitHub Actions 工作流和文档采用 [MIT License](LICENSE)。
- `upstream/` 中的内容受上游许可证约束。GitHub API 报告的上游许可证为：`MIT`。

---

<div align="center">

本仓库只是镜像，不是上游项目官方仓库。

[返回顶部](#linuxdo-idea-ui-bak)

</div>
