# OpenClaw Docs 文件夹分析

## 概述

OpenClaw 是一个多平台 AI 代理网关，将 WhatsApp、Telegram、Discord、iMessage 等消息平台与 AI 编码代理（Pi）桥接起来。文档主要使用 Mintlify 作为文档框架。

---

## 核心目录结构

### 📁 概念 (`concepts/`) - 30 个文件

核心概念文档，涵盖系统架构和工作原理：

| 文件 | 描述 |
|------|------|
| `architecture.md` | 系统整体架构 |
| `agent.md` / `agent-loop.md` / `agent-workspace.md` | AI 代理相关概念 |
| `session.md` / `session-tool.md` / `session-pruning.md` | 会话管理 |
| `multi-agent.md` | 多代理路由 |
| `streaming.md` | 流式响应处理 |
| `memory.md` | 记忆系统 |
| `models.md` / `model-failover.md` / `model-providers.md` | 模型配置与故障转移 |
| `context.md` / `compaction.md` | 上下文管理与压缩 |
| `groups.md` / `group-messages.md` | 群组消息处理 |
| `queue.md` | 消息队列 |
| `oauth.md` | OAuth 认证 |
| `presence.md` / `typing-indicators.md` | 在线状态与输入指示器 |

---

### 📁 命令行工具 (`cli/`) - 41 个文件

完整的 CLI 命令文档：

| 命令类别 | 核心命令 |
|----------|----------|
| **网关管理** | `gateway.md`, `doctor.md`, `status.md`, `health.md` |
| **消息操作** | `message.md`, `sessions.md` |
| **配置** | `config.md`, `configure.md` |
| **渠道** | `channels.md` |
| **代理** | `agent.md`, `agents.md` |
| **节点** | `node.md`, `nodes.md` |
| **钩子/自动化** | `hooks.md`, `cron.md`, `webhooks.md` |
| **沙盒** | `sandbox.md` |
| **安装** | `onboard.md`, `setup.md`, `update.md`, `uninstall.md` |
| **工具** | `browser.md`, `voicecall.md`, `tui.md` |

---

### 📁 渠道 (`channels/`) - 22 个文件

支持的消息平台集成：

| 平台类型 | 支持的渠道 |
|----------|------------|
| **即时通讯** | WhatsApp, Telegram, Discord, iMessage, Signal, Slack |
| **协作工具** | Mattermost, Microsoft Teams, Google Chat |
| **亚洲平台** | LINE, Zalo |
| **其他** | Matrix, Nostr, Twitch, Nextcloud Talk, Tlon, BlueBubbles |

每个渠道文档包含配置方法、Bot 创建步骤、权限设置等。

---

### 📁 网关 (`gateway/`) - 27 个文件 + 1 子目录

核心网关配置和操作：

| 类别 | 文件 |
|------|------|
| **配置** | `configuration.md` (117KB，最大的文档), `configuration-examples.md` |
| **安全** | `authentication.md`, `security/` 子目录, `sandboxing.md` |
| **网络** | `discovery.md`, `remote.md`, `tailscale.md`, `bonjour.md` |
| **诊断** | `doctor.md`, `troubleshooting.md`, `health.md`, `logging.md` |
| **协议** | `protocol.md`, `bridge-protocol.md`, `openai-http-api.md` |
| **其他** | `heartbeat.md`, `pairing.md`, `local-models.md` |

---

### 📁 平台 (`platforms/`) - 14 个文件 + 1 子目录

各操作系统和云平台部署指南：

| 类别 | 平台 |
|------|------|
| **桌面** | macOS (`mac/` 子目录含 18 个文件), Windows, Linux |
| **移动** | iOS, Android |
| **云服务** | Fly.io, GCP, Hetzner, DigitalOcean, Oracle |
| **单板电脑** | Raspberry Pi |
| **虚拟化** | macOS VM |

---

### 📁 工具 (`tools/`) - 22 个文件

Agent 可用的工具和功能：

| 工具类别 | 描述 |
|----------|------|
| `browser.md` | 浏览器自动化 |
| `exec.md` | 命令执行 |
| `skills.md` / `skills-config.md` | 技能系统 |
| `slash-commands.md` | 斜杠命令 |
| `subagents.md` | 子代理 |
| `clawhub.md` | ClawHub 技能仓库 |
| `thinking.md` | 思考模式 |
| `elevated.md` | 提权操作 |
| `web.md` | Web 工具 |

---

### 📁 提供商 (`providers/`) - 19 个文件

AI 模型提供商配置：

| 提供商 | 描述 |
|--------|------|
| `anthropic.md` | Claude 系列模型 |
| `openai.md` | GPT 系列模型 |
| `ollama.md` | 本地模型 |
| `openrouter.md` | 多模型路由 |
| `minimax.md`, `moonshot.md` | 中国 AI 提供商 |
| `qwen.md`, `glm.md`, `xiaomi.md`, `zai.md` | 更多中国提供商 |
| `venice.md` | Venice AI |
| `deepgram.md` | 语音转文字 |
| `github-copilot.md` | GitHub Copilot |

---

### 📁 自动化 (`automation/`) - 6 个文件

自动化和定时任务：

- `cron-jobs.md` - 定时任务
- `webhook.md` - Webhook 集成
- `gmail-pubsub.md` - Gmail Pub/Sub 钩子
- `poll.md` - 轮询任务
- `auth-monitoring.md` - 认证监控
- `cron-vs-heartbeat.md` - Cron vs 心跳对比

---

### 📁 其他重要目录

| 目录 | 内容 |
|------|------|
| `start/` (9 文件) | 入门指南、向导、配对设置 |
| `install/` (11 文件) | 安装方法：npm, Docker, Nix, Bun 等 |
| `reference/` (19 文件) | API 参考、模板、RPC 文档 |
| `nodes/` (8 文件) | 节点配置（图片、音频、摄像头、位置等） |
| `web/` (4 文件) | Web 界面：Control UI, WebChat, Dashboard |
| `help/` (3 文件) | FAQ 和故障排除 |
| `plugins/` (4 文件) | 插件开发 |
| `experiments/` (6 文件) | 实验性功能和提案 |
| `refactor/` (5 文件) | 重构计划 |

---

## 根目录重要文件

| 文件 | 描述 |
|------|------|
| `index.md` | 主页，项目概述 |
| `docs.json` | Mintlify 文档配置，包含导航和重定向 |
| `hooks.md` | 钩子系统详细文档 (19KB) |
| `pi.md` | Pi 代理文档 (26KB) |
| `plugin.md` | 插件开发指南 |
| `testing.md` | 测试指南 |
| `logging.md` | 日志系统 |
| `tts.md` | 文字转语音 |

---

## 国际化

- `zh-CN/` 目录包含 3 个中文文档
- `docs.json` 顶部导航含中文链接

---

## 核心功能总结

1. **多渠道网关** - 统一集成 WhatsApp、Telegram、Discord、iMessage 等
2. **AI 代理桥接** - 连接 Pi 编码代理
3. **多平台部署** - 支持 macOS、iOS、Android、云服务
4. **技能系统** - 可扩展的 Agent 能力
5. **会话管理** - 智能上下文和记忆
6. **自动化** - Cron、Webhook、Gmail 集成
7. **安全** - 沙盒、认证、权限控制
