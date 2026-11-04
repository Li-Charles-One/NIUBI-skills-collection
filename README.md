# NIUBI Skills Collection

精选第三方 AI Agent Skill 合集。只收录别人的官方 skill，不放自研包。

适配：Claude Code / Codex / 豆包 / OpenCode 等支持 `SKILL.md` 的 Agent。

收录方式：

- **git submodule**：上游有独立 Git 仓（或 CLI+skill 发在同一个仓）
- **直接收录（vendor）**：上游只有 zip / CDN，没有可跟的 skill Git 仓

## 使用方法

```bash
git clone --recurse-submodules https://github.com/Li-Charles-One/NIUBI-skills-collection.git
```

已克隆但子模块为空：

```bash
git submodule update --init --recursive
```

更新所有子模块：

```bash
git submodule update --remote --merge
```

vendor 包（`aihot` / `dreamina-cli`）需对照各节里的官方地址手动更新。

## `skills/` 每个文件夹

### `skills/tavily-skills/`

Tavily 官方 Agent Skills：网页搜索、抽取、爬取、站点地图、深度研究。

- 收录：submodule → [tavily-ai/skills](https://github.com/tavily-ai/skills)
- Agent 用：`skills/tavily-cli` 等子目录（仓内 `skills/`）
- 官方 CLI（`tvly`）：`curl -fsSL https://cli.tavily.com/install.sh | bash`  
  或 `uv tool install tavily-cli`；CLI 仓：[tavily-ai/tavily-cli](https://github.com/tavily-ai/tavily-cli)

### `skills/firecrawl-cli/`

Firecrawl 官方 CLI 仓（CLI 与 skill 发在一起）：搜索、抓取、爬取、交互。

- 收录：submodule → [firecrawl/cli](https://github.com/firecrawl/cli)
- Agent 用：`skills/firecrawl/` 主 skill（仓内 `skills/firecrawl`），另有 11 个分工 skill：search / scrape / crawl / map / interact / monitor / download / parse / agent / developer-index / research-index
- 官方 CLI：`npm install -g firecrawl-cli`  
  或 `curl -fsSL https://firecrawl.dev/install.sh | bash`

### `skills/context7/`

Context7 官方平台仓（文档检索 CLI/MCP 与 skill 发在一起）。

- 收录：submodule → [upstash/context7](https://github.com/upstash/context7)
- Agent 用：`skills/find-docs/`（仓内 `skills/find-docs`）
- 官方 CLI（`ctx7`）：见上游 README / `npx ctx7`

### `skills/officecli/`

OfficeCLI 官方 CLI+skill：读写编辑 Word / Excel / PowerPoint，无需安装 Office。

- 收录：submodule → [iOfficeAI/OfficeCLI](https://github.com/iOfficeAI/OfficeCLI)
- Agent 用：本目录根 `SKILL.md`（另有仓内 `skills/` 下 11 个细分 skill：docx / xlsx / pptx 等）
- 官方 CLI：`curl -fsSL https://d.officecli.ai/install.sh | bash`（Windows：`irm https://d.officecli.ai/install.ps1 | iex`）

### `skills/quarkclouddrive/`

夸克网盘官方 skill：上传下载、分享转存、搜索、相册、AI 助手。

- 收录：submodule → [quark-clouddrive/quarkclouddrive_offical](https://github.com/quark-clouddrive/quarkclouddrive_offical)
- Agent 用：`skills/quarkclouddrive/`（仓内 `skills/quarkclouddrive`）
- 官方 CLI：首次在 skill 目录执行 `bash scripts/install.sh`（随官方包提供，不要用 `quark-drive.cjs update` 升级文档）

### `skills/aihot/`

AIHOT 中文 AI 资讯查询 skill（日报 / 精选 / 热点）。零配置，匿名 HTTP API。

- 收录：vendor（无独立 Git 仓，当前 v1.6.0）
- 官方包：<https://aihot.virxact.com/aihot-skill/README.md>
- GitHub 镜像：[KKKKhazix/khazix-skills/aihot](https://github.com/KKKKhazix/khazix-skills/tree/main/aihot)
- Agent 用：本目录根 `SKILL.md`
- 无 CLI

### `skills/dreamina-cli/`

即梦（Dreamina）官方 CLI skill：登录、会话、积分、文生图/视频、任务查询与下载。

- 收录：vendor（官方只随 CLI 发 `SKILL.md`，无 GitHub 仓）
- Agent 用：本目录根 `SKILL.md`（来自官方安装器写入的副本）
- 官方 CLI 安装：

```bash
curl -fsSL https://jimeng.jianying.com/cli | bash
```

安装后二进制一般在 `~/.local/bin/dreamina`（Windows 常见 `~/bin/dreamina.exe`），官方 skill 落到 `~/.dreamina_cli/dreamina/SKILL.md`。

### `skills/sureforge/`

SureForge 复杂任务质量管控 Skill（Da7-Tech 出品）：先调研再问、问完再规划、冻结版本全量验、独立 reviewer 审过才交付，防返工。

- 收录：submodule → [Da7-Tech/SureForge](https://github.com/Da7-Tech/SureForge)
- Agent 用：`skills/sureforge/`（仓内 `skills/sureforge`，内含 `SKILL.md` 与 `references/`、`assets/`）
- 官方安装方式：`npx skills add Da7-Tech/SureForge`

### `skills/remotion-skills/`

Remotion 官方 Agent Skills：React 视频编程最佳实践、组件与动画规范、Studio 预览与交互、地图动画、字幕、多媒体处理、SaaS 集成与官方文档检索。

- 收录：submodule → [remotion-dev/skills](https://github.com/remotion-dev/skills)
- Agent 用：`skills/remotion-best-practices/` 主入口（仓内 `skills/remotion-best-practices`，已内嵌全部子模块引用；另有 11 个独立细分 skill：`remotion-create` / `remotion-markup` / `remotion-studio` / `remotion-render` / `remotion-maps` / `remotion-captions` / `remotion-saas` / `remotion-interactivity` / `remotion-docs` / `remotion-upgrade` / `remotion-multimedia`）
- 官方安装方式：`npx skills add remotion-dev/skills` 或 `gh skill install remotion-dev/skills`

### `skills/video-shotcraft/`

video-shotcraft 电影感产品宣传片 Skill（Vincentwei1021 出品）：基于 Remotion、真实页面抓取、124 张镜头配方卡（150 个镜头）、Ink Press 模板、音乐卡点与音效设计制作产品视频，支持导出剪映专业版草稿。

- 收录：submodule → [Vincentwei1021/video-shotcraft](https://github.com/Vincentwei1021/video-shotcraft)
- Agent 用：本目录根 `SKILL.md`（内含 `references/`、`demos/`、`template/`、`jianying-export/` 等）
- 官方安装方式：`npx skills add Vincentwei1021/video-shotcraft`

### `skills/mole/`

Mole 官方 CLI+skill（tw93 出品）：Mac/PC 磁盘占用分析、缓存清理（先 `--dry-run` 预览）、应用卸载、系统健康与清理历史。

- 收录：submodule → [tw93/Mole](https://github.com/tw93/Mole)
- Agent 用：`.agents/skills/mole/`（仓内隐藏目录，内含 `SKILL.md` 与 `references/`）
- 官方 CLI（`mo`）：`brew install mole`
- 官方安装方式：`npx skills add tw93/Mole`

## 目录一览

```
NIUBI-skills-collection/
└── skills/
    ├── tavily-skills/        submodule  tavily-ai/skills
    ├── firecrawl-cli/        submodule  firecrawl/cli
    ├── context7/             submodule  upstash/context7
    ├── officecli/            submodule  iOfficeAI/OfficeCLI
    ├── quarkclouddrive/      submodule  quark-clouddrive/quarkclouddrive_offical
    ├── aihot/                vendor     AIHOT 官方 skill 包
    ├── dreamina-cli/         vendor     即梦官方 CLI skill
    ├── sureforge/            submodule  Da7-Tech/SureForge
    ├── remotion-skills/      submodule  remotion-dev/skills
    ├── video-shotcraft/      submodule  Vincentwei1021/video-shotcraft
    └── mole/                 submodule  tw93/Mole
```

## 贡献

发现好用的官方 Skill？提 Issue 或 PR。有 Git 仓优先 submodule；只有 zip/CDN 再 vendor，并在本节写清官方安装地址。
