# OpenClaw Skills 文件夹分析

## 概述

Skills（技能）是 OpenClaw 的模块化扩展系统，为 AI 代理提供专业领域知识、工作流程和工具集成。每个技能包含一个必需的 `SKILL.md` 文件和可选的脚本/资源。

---

## 技能目录结构标准

```
skill-name/
├── SKILL.md          # 必需：技能定义和说明
├── scripts/          # 可选：可执行脚本
├── references/       # 可选：参考文档
└── assets/           # 可选：模板、图标等资源
```

### SKILL.md 文件格式

```yaml
---
name: skill-name                    # 技能名称
description: "技能描述和触发条件"    # 技能描述
homepage: https://example.com       # 可选：主页
metadata:
  openclaw:
    emoji: "🔧"                     # 技能图标
    requires:
      bins: ["command"]             # 需要的命令行工具
      config: ["channels.xxx"]      # 需要的配置项
    install: [...]                  # 安装方式
---

# 技能正文（Markdown 格式）
```

---

## 全部 52 个技能分类

### 🐦 社交媒体 (4)

| 技能 | 描述 | 依赖 |
|------|------|------|
| `bird` | X/Twitter CLI：阅读、搜索、发帖、互动 | `bird` CLI |
| `discord` | Discord 控制：消息、表情、投票、管理 | 配置 `channels.discord` |
| `slack` | Slack 控制：表情、固定消息、发送消息 | 配置 `channels.slack` |
| `wacli` | WhatsApp CLI 工具 | `wacli` |

### 💬 通讯工具 (4)

| 技能 | 描述 |
|------|------|
| `bluebubbles` | BlueBubbles iMessage 客户端 |
| `imsg` | iMessage CLI 工具 (macOS) |
| `himalaya` | 邮件 CLI（支持 IMAP/SMTP） |
| `voice-call` | 语音通话功能 |

### 🐙 开发工具 (4)

| 技能 | 描述 | 依赖 |
|------|------|------|
| `github` | GitHub CLI：Issues、PRs、Workflow | `gh` CLI |
| `coding-agent` | 编程代理增强 | - |
| `gemini` | Google Gemini 集成 | - |
| `trello` | Trello 看板管理 | - |

### 📝 笔记与待办 (7)

| 技能 | 描述 |
|------|------|
| `apple-notes` | Apple Notes 集成 (macOS) |
| `apple-reminders` | Apple Reminders 集成 (macOS) |
| `bear-notes` | Bear 笔记应用集成 |
| `notion` | Notion 集成 |
| `obsidian` | Obsidian 知识库集成 |
| `things-mac` | Things 3 待办应用 (macOS) |
| `canvas` | Canvas 绘图工具 |

### 🌤️ 实用工具 (8)

| 技能 | 描述 | 依赖 |
|------|------|------|
| `weather` | 天气查询（wttr.in/Open-Meteo） | `curl` |
| `goplaces` | 地点搜索和推荐 | - |
| `local-places` | 本地地点信息（含 7 个文件） | - |
| `food-order` | 食品订购 | - |
| `ordercli` | 订单管理 CLI | - |
| `1password` | 1Password 密码管理（含 3 个文件） | - |
| `camsnap` | 摄像头快照 | - |
| `peekaboo` | 屏幕截图工具 (macOS) | - |

### 🎵 媒体 (6)

| 技能 | 描述 |
|------|------|
| `spotify-player` | Spotify 播放控制 |
| `sonoscli` | Sonos 音响控制 |
| `songsee` | 音乐识别 |
| `openhue` | Philips Hue 灯光控制 |
| `video-frames` | 视频帧提取（含 2 个文件） |
| `gifgrep` | GIF 搜索 |

### 🤖 AI 与语音 (4)

| 技能 | 描述 |
|------|------|
| `openai-image-gen` | OpenAI 图像生成（DALL-E） |
| `openai-whisper` | OpenAI Whisper 语音转文字（本地） |
| `openai-whisper-api` | OpenAI Whisper API（含 2 个文件） |
| `sherpa-onnx-tts` | Sherpa-ONNX 文字转语音 |

### 📊 数据与监控 (4)

| 技能 | 描述 |
|------|------|
| `model-usage` | 模型使用统计（含 3 个文件） |
| `session-logs` | 会话日志 |
| `blogwatcher` | 博客监控 |
| `summarize` | 内容摘要 |

### 🔧 系统与终端 (4)

| 技能 | 描述 |
|------|------|
| `tmux` | Tmux 终端管理（含 3 个文件） |
| `blucli` | Bluetooth CLI 工具 |
| `eightctl` | 8BitDo 控制器管理 |
| `nano-banana-pro` | Nano Banana Pro 设备控制（含 2 个文件） |

### 📄 文档处理 (2)

| 技能 | 描述 |
|------|------|
| `nano-pdf` | PDF 处理 |
| `oracle` | Oracle 数据库/知识库 |

### 🎮 游戏 (2)

| 技能 | 描述 |
|------|------|
| `gog` | GOG 游戏平台 |
| `mcporter` | Minecraft 移植工具 |

### 🛠️ 技能开发 (2)

| 技能 | 描述 |
|------|------|
*| `skill-creator` | 技能创建指南（含 5 个文件） |
| `clawhub` | ClawHub 技能仓库集成 |*

### 🔎 搜索与代理 (1)

| 技能 | 描述 |
|------|------|
| `sag` | 搜索代理 |

---

## 重点技能详解

### 🐦 bird（X/Twitter）

功能丰富的 X/Twitter CLI 工具：
- **阅读**：读取推文、时间线、回复
- **搜索**：高级搜索支持
- **发帖**：发推、回复、附带媒体
- **互动**：关注/取关、书签、点赞
- **分页**：支持批量获取

依赖 cookie 认证，支持 Chrome/Firefox/Arc 浏览器。

### 🐙 github

GitHub CLI 集成：
```bash
gh pr checks 55 --repo owner/repo    # 检查 PR CI 状态
gh run list --repo owner/repo        # 列出 workflow 运行
gh run view <id> --log-failed        # 查看失败日志
gh api repos/owner/repo/pulls/55     # API 查询
```

### 🎮 discord

功能全面的 Discord 控制：
- 消息：读取、发送、编辑、删除
- 表情：添加表情反应
- 投票：创建投票
- 贴纸：发送和上传贴纸
- 线程：创建和管理线程
- 管理：频道管理、角色管理（默认禁用）

### 💬 slack

Slack 工作区控制：
- 消息操作：发送、编辑、删除
- 表情反应
- 固定消息
- 成员信息查询
- 自定义表情列表

### 🌤️ weather

无需 API Key 的天气查询：
```bash
# wttr.in（主要）
curl -s "wttr.in/London?format=3"
# 输出：London: ⛅️ +8°C

# Open-Meteo（备用，JSON）
curl -s "https://api.open-meteo.com/v1/forecast?..."
```

### 🛠️ skill-creator

技能创建完整指南：
1. **理解技能**：收集具体用例
2. **规划内容**：确定脚本、参考文档、资源
3. **初始化**：运行 `init_skill.py`
4. **编辑**：实现资源和 SKILL.md
5. **打包**：运行 `package_skill.py`
6. **迭代**：基于实际使用改进

---

## 技能系统核心原则

### 1. 简洁优先
上下文窗口有限，技能应只包含 AI 不知道的信息。

### 2. 渐进式披露
- **元数据**（始终加载）：~100 词
- **SKILL.md 正文**（触发时加载）：<5000 词
- **资源文件**（按需加载）：无限制

### 3. 适当的自由度
- **高自由度**：文本指导，多种方法有效
- **中等自由度**：伪代码或带参数脚本
- **低自由度**：具体脚本，操作需精确执行

---

## 技能安装方式

技能通过 `metadata.openclaw.install` 定义安装方式：

| 类型 | 示例 |
|------|------|
| `brew` | Homebrew 安装 (macOS) |
| `apt` | APT 包管理器 (Linux) |
| `node` | npm/pnpm 全局安装 |
| `config` | 配置依赖（如 `channels.discord`） |

---

## 统计摘要

| 指标 | 数量 |
|------|------|
| 总技能数 | 52 |
| 含多文件的技能 | 12 |
| 社交媒体相关 | 4 |
| 开发工具相关 | 4 |
| 笔记/待办相关 | 7 |
| AI/语音相关 | 4 |
