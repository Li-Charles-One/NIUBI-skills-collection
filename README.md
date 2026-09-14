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

vendor 包（`aihot` / `libtv-cli` / `dreamina-cli`）需对照各节里的官方地址手动更新。

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

### `skills/tikhub-agent-skill/`

TikHub 官方独立 skill：抖音 / TikTok / 小红书等社媒数据，走 MCP。

- 收录：submodule → [MangouArt/tikhub-agent-skill](https://github.com/MangouArt/tikhub-agent-skill)
- Agent 用：本目录根 `SKILL.md`
- 无独立 CLI；需要环境变量 `TIKHUB_API_KEY`，MCP：`https://mcp.tikhub.io`

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

### `skills/libtv-cli/`

LibTV 官方 CLI skill：用 `libtv` 操作画布 / 项目 / 节点 / 模型 / 素材。

- 收录：vendor（官方 skill zip，无对应 Git 仓）
- Agent 用：本目录根 `SKILL.md`
- 官方 CLI / skill zip 入口（权威，不要手拼版本路径）：  
  `https://api2.liblib.art/api/www/landing-activities/getById?id=240`  
  解析 `data.linkUrl` 里的 `install.*` 与 `skill`。  
  一键脚本示例：`https://liblibai-web-static.liblib.cloud/cli/latest/install-libtv-cli.sh`  
  详情见本目录 `scripts/install.md`。  
  注意：[libtv-labs/libtv-skills](https://github.com/libtv-labs/libtv-skills) 是另一套 IM OpenAPI skill，不是本包。

### `skills/lark-cli/`

飞书 / Lark 官方 CLI 仓（`lark-cli` 与 20+ 个 `lark-*` skill 发在一起）：文档、云盘、IM、日历、多维表格、任务等。

- 收录：submodule → [larksuite/cli](https://github.com/larksuite/cli)
- Agent 用：仓内 `skills/lark-doc`、`skills/lark-im`、`skills/lark-shared` 等（不要把整个 CLI 源码当 skill 根目录加载）
- 官方 CLI / skill 安装：

```bash
npx skills add larksuite/cli -y -g
```

或见上游 README：`git clone` + `make install`。认证：`lark-cli auth login`。

### `skills/dreamina-cli/`

即梦（Dreamina）官方 CLI skill：登录、会话、积分、文生图/视频、任务查询与下载。

- 收录：vendor（官方只随 CLI 发 `SKILL.md`，无 GitHub 仓）
- Agent 用：本目录根 `SKILL.md`（来自官方安装器写入的副本）
- 官方 CLI 安装：

```bash
curl -fsSL https://jimeng.jianying.com/cli | bash
```

安装后二进制一般在 `~/.local/bin/dreamina`（Windows 常见 `~/bin/dreamina.exe`），官方 skill 落到 `~/.dreamina_cli/dreamina/SKILL.md`。

### `skills/hallmark/`

Hallmark 官方反 AI 烂俗味前端设计规范 Skill（Together AI / Nutlope 出品）：拒绝 AI 生成感、21 种艺术主题、57 道质量门禁、代码体检、重构与 DNA 逆向提取。

- 收录：submodule → [Nutlope/hallmark](https://github.com/Nutlope/hallmark)
- Agent 用：`skills/hallmark/`（仓内 `skills/hallmark`，内含 `SKILL.md` 与 `references/`）
- 官方安装方式：`npx skills add nutlope/hallmark`

### `skills/sureforge/`

SureForge 复杂任务质量管控 Skill（Da7-Tech 出品）：先调研再问、问完再规划、冻结版本全量验、独立 reviewer 审过才交付，防返工。

- 收录：submodule → [Da7-Tech/SureForge](https://github.com/Da7-Tech/SureForge)
- Agent 用：`skills/sureforge/`（仓内 `skills/sureforge`，内含 `SKILL.md` 与 `references/`、`assets/`）
- 官方安装方式：`npx skills add Da7-Tech/SureForge`

## 目录一览

```
NIUBI-skills-collection/
└── skills/
    ├── tavily-skills/        submodule  tavily-ai/skills
    ├── firecrawl-cli/        submodule  firecrawl/cli
    ├── context7/             submodule  upstash/context7
    ├── officecli/            submodule  iOfficeAI/OfficeCLI
    ├── tikhub-agent-skill/   submodule  MangouArt/tikhub-agent-skill
    ├── quarkclouddrive/      submodule  quark-clouddrive/quarkclouddrive_offical
    ├── lark-cli/             submodule  larksuite/cli
    ├── aihot/                vendor     AIHOT 官方 skill 包
    ├── libtv-cli/            vendor     LibTV 官方 CLI skill zip
    ├── dreamina-cli/         vendor     即梦官方 CLI skill
    ├── hallmark/             submodule  Nutlope/hallmark
    └── sureforge/            submodule  Da7-Tech/SureForge
```

## 贡献

发现好用的官方 Skill？提 Issue 或 PR。有 Git 仓优先 submodule；只有 zip/CDN 再 vendor，并在本节写清官方安装地址。
