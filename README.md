# NIUBI Skills Collection

精选优质 AI Agent Skill 合集，以 Git 子模块方式组织，方便追踪原仓库更新。

适配平台：Claude Code / Codex / 豆包 / 任何支持 Skill 的 AI Agent。

## 使用方法

克隆本仓库（含子模块）：

```bash
git clone --recurse-submodules https://github.com/Li-Charles-One/NIUBI-skills-collection.git
```

已克隆但子模块为空？执行：

```bash
git submodule update --init --recursive
```

更新所有子模块到最新版本：

```bash
git submodule update --remote --merge
```

## Skills 列表

| Skill | 功能 | 平台 | 链接 |
|-------|------|------|------|
| [aihot](./skills/aihot) | 中文 AI 资讯查询（AI HOT 日报/精选/热点），零配置 curl 公开 API | Claude Code / Codex / OpenCode 等 | [上游](https://github.com/KKKKhazix/khazix-skills/tree/main/aihot) |
| [tavily-skills](./skills/tavily-skills) | Tavily 官方：网页搜索 / 抽取 / 爬取 / 地图 / 深度研究（配合 CLI `tvly`） | Claude Code / Codex / OpenCode 等 | [原仓库](https://github.com/tavily-ai/skills) |
| [firecrawl-cli](./skills/firecrawl-cli) | Firecrawl 官方 CLI + Agent Skill：搜索 / 抓取 / 爬取 / 交互 | Claude Code / Codex / OpenCode 等 | [原仓库](https://github.com/firecrawl/cli) |
| [context7](./skills/context7) | Context7 官方：最新库文档检索（主 skill：`find-docs`，配合 CLI `ctx7`） | Claude Code / Codex / OpenCode 等 | [原仓库](https://github.com/upstash/context7) |
| [officecli](./skills/officecli) | OfficeCLI 官方：读写编辑 Word / Excel / PowerPoint（CLI Skill） | Claude Code / Codex / OpenCode 等 | [原仓库](https://github.com/iOfficeAI/OfficeCLI) |
| [tikhub-agent-skill](./skills/tikhub-agent-skill) | TikHub 单 skill：抖音/TikTok/小红书等 16+ 平台社媒数据（MCP，需 `TIKHUB_API_KEY`） | Claude Code / Codex / OpenCode 等 | [原仓库](https://github.com/MangouArt/tikhub-agent-skill) |
| [libtv-cli](./skills/libtv-cli) | LibTV 官方 CLI：画布 / 项目 / 节点 / 模型 / 素材 | Claude Code / Codex / OpenCode 等 | 直接收录（配合 `libtv` CLI） |
| [quarkclouddrive](./skills/quarkclouddrive) | 夸克网盘官方：上传/下载、分享转存、搜索、相册整理、AI 助手 | Claude Code / Codex / OpenCode 等 | 直接收录（官方 Skill zip v1.0.14） |

## 目录结构

```
NIUBI-skills-collection/
└── skills/
    ├── tavily-skills/       ← git submodule（tavily-ai/skills）
    ├── firecrawl-cli/       ← git submodule（firecrawl/cli）
    ├── context7/            ← git submodule（upstash/context7；用 skills/find-docs）
    ├── officecli/           ← git submodule（iOfficeAI/OfficeCLI）
    ├── tikhub-agent-skill/  ← git submodule（MangouArt/tikhub-agent-skill）
    ├── aihot/               ← 直接收录（上游无独立仓）
    ├── libtv-cli/           ← 直接收录（LibTV CLI skill）
    └── quarkclouddrive/     ← 直接收录（夸克网盘官方 Skill）
```

## 贡献

发现好用的 Skill？欢迎提 Issue 推荐或直接 PR 添加子模块。
