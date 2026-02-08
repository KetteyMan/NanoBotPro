<div align="center">
  <img src="nanobot_logo.png" alt="nanobot" width="500">
  <h1>nanobot：超轻量个人 AI 助手</h1>
  <p>中文 | <a href="./README.md">English</a></p>
  <p>
    <a href="https://pypi.org/project/nanobot-ai/"><img src="https://img.shields.io/pypi/v/nanobot-ai" alt="PyPI"></a>
    <a href="https://pepy.tech/project/nanobot-ai"><img src="https://static.pepy.tech/badge/nanobot-ai" alt="Downloads"></a>
    <img src="https://img.shields.io/badge/python-≥3.11-blue" alt="Python">
    <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
    <a href="./COMMUNICATION.md"><img src="https://img.shields.io/badge/Feishu-Group-E9DBFC?style=flat&logo=feishu&logoColor=white" alt="Feishu"></a>
    <a href="./COMMUNICATION.md"><img src="https://img.shields.io/badge/WeChat-Group-C5EAB4?style=flat&logo=wechat&logoColor=white" alt="WeChat"></a>
    <a href="https://discord.gg/MnCvHqpUGB"><img src="https://img.shields.io/badge/Discord-Community-5865F2?style=flat&logo=discord&logoColor=white" alt="Discord"></a>
  </p>
</div>

🐈 **nanobot** 是一款受 [Clawdbot](https://github.com/openclaw/openclaw) 启发的**超轻量**个人 AI 助手。

⚡️ 仅用约 **4,000** 行核心代码实现完整智能体能力 —— 相比 Clawdbot 的 43 万+ 行代码**精简约 99%**。

📏 实时行数：**3,423 行**（可随时运行 `bash core_agent_lines.sh` 自行验证）

## 📢 动态

- **2026-02-07** 🚀 发布 v0.1.3.post5，支持 Qwen 及多项改进！详见[发布说明](https://github.com/HKUDS/nanobot/releases/tag/v0.1.3.post5)。
- **2026-02-06** ✨ 新增 Moonshot/Kimi 提供商、Discord 集成及安全加固！
- **2026-02-05** ✨ 新增飞书通道、DeepSeek 提供商及增强的定时任务支持！
- **2026-02-04** 🚀 发布 v0.1.3.post4，支持多提供商与 Docker！详见[发布说明](https://github.com/HKUDS/nanobot/releases/tag/v0.1.3.post4)。
- **2026-02-03** ⚡ 集成 vLLM 支持本地大模型，并改进自然语言定时任务！
- **2026-02-02** 🎉 nanobot 正式发布！欢迎体验 🐈 nanobot！

## nanobot 核心特点

🪶 **超轻量**：核心智能体代码仅约 4,000 行，比 Clawdbot 精简约 99%。

🔬 **适合研究**：代码清晰可读，便于理解、修改和扩展，适合研究与二次开发。

⚡️ **启动快**：体积小，启动更快、资源占用更低、迭代更迅速。

💎 **易上手**：一键部署即可使用。

## 🏗️ 架构

<p align="center">
  <img src="nanobot_arch.png" alt="nanobot 架构" width="800">
</p>

## ✨ 功能概览

<table align="center">
  <tr align="center">
    <th><p align="center">📈 24/7 实时市场分析</p></th>
    <th><p align="center">🚀 全栈软件工程师</p></th>
    <th><p align="center">📅 智能日程管理</p></th>
    <th><p align="center">📚 个人知识助手</p></th>
  </tr>
  <tr>
    <td align="center"><p align="center"><img src="case/search.gif" width="180" height="400"></p></td>
    <td align="center"><p align="center"><img src="case/code.gif" width="180" height="400"></p></td>
    <td align="center"><p align="center"><img src="case/scedule.gif" width="180" height="400"></p></td>
    <td align="center"><p align="center"><img src="case/memory.gif" width="180" height="400"></p></td>
  </tr>
  <tr>
    <td align="center">发现 • 洞察 • 趋势</td>
    <td align="center">开发 • 部署 • 扩展</td>
    <td align="center">排程 • 自动化 • 整理</td>
    <td align="center">学习 • 记忆 • 推理</td>
  </tr>
</table>

## 📦 安装

**从源码安装**（最新功能，推荐开发使用）

```bash
git clone https://github.com/HKUDS/nanobot.git
cd nanobot
pip install -e .
```

**使用 [uv](https://github.com/astral-sh/uv) 安装**（稳定、快速）

```bash
uv tool install nanobot-ai
```

**从 PyPI 安装**（稳定版）

```bash
pip install nanobot-ai
```

## 🚀 快速开始

> [!TIP]
> 在 `~/.nanobot/config.json` 中配置 API 密钥。
> 获取 API 密钥：[OpenRouter](https://openrouter.ai/keys)（全球）· [DashScope](https://dashscope.console.aliyun.com)（通义千问）· [Brave Search](https://brave.com/search/api/)（可选，用于网页搜索）

**1. 初始化**

```bash
nanobot onboard
```

**2. 配置**（`~/.nanobot/config.json`）

使用 OpenRouter（推荐全球用户）：
```json
{
  "providers": {
    "openrouter": {
      "apiKey": "sk-or-v1-xxx"
    }
  },
  "agents": {
    "defaults": {
      "model": "anthropic/claude-opus-4-5"
    }
  }
}
```

**3. 对话**

```bash
nanobot agent -m "2+2 等于几？"
```

两分钟内即可拥有可用的 AI 助手。

## 🖥️ 本地模型（vLLM）

通过 vLLM 或任意 OpenAI 兼容服务，使用本地模型运行 nanobot。

**1. 启动 vLLM 服务**

```bash
vllm serve meta-llama/Llama-3.1-8B-Instruct --port 8000
```

**2. 配置**（`~/.nanobot/config.json`）

```json
{
  "providers": {
    "vllm": {
      "apiKey": "dummy",
      "apiBase": "http://localhost:8000/v1"
    }
  },
  "agents": {
    "defaults": {
      "model": "meta-llama/Llama-3.1-8B-Instruct"
    }
  }
}
```

**3. 对话**

```bash
nanobot agent -m "你好，来自我的本地大模型！"
```

> [!TIP]
> 本地服务若不要求鉴权，`apiKey` 可为任意非空字符串。

## 💬 聊天应用

通过 Telegram、Discord、WhatsApp 或飞书与 nanobot 对话，随时随地。

| 通道 | 配置难度 |
|------|----------|
| **Telegram** | 简单（仅需 token） |
| **Discord** | 简单（机器人 token + 权限） |
| **WhatsApp** | 中等（扫码绑定） |
| **飞书** | 中等（应用凭证） |

<details>
<summary><b>Telegram</b>（推荐）</summary>

**1. 创建机器人**
- 打开 Telegram，搜索 `@BotFather`
- 发送 `/newbot`，按提示操作
- 复制得到的 token

**2. 配置**

```json
{
  "channels": {
    "telegram": {
      "enabled": true,
      "token": "YOUR_BOT_TOKEN",
      "allowFrom": ["YOUR_USER_ID"]
    }
  }
}
```

> 在 Telegram 中向 `@userinfobot` 获取你的用户 ID。

**3. 运行**

```bash
nanobot gateway
```

</details>

<details>
<summary><b>Discord</b></summary>

**1. 创建机器人**
- 打开 https://discord.com/developers/applications
- 创建应用 → Bot → Add Bot
- 复制 Bot Token

**2. 开启权限**
- 在 Bot 设置中启用 **MESSAGE CONTENT INTENT**
- （可选）若需基于成员数据的白名单，可启用 **SERVER MEMBERS INTENT**

**3. 获取你的用户 ID**
- Discord 设置 → 高级 → 开启 **开发者模式**
- 右键你的头像 → **复制用户 ID**

**4. 配置**

```json
{
  "channels": {
    "discord": {
      "enabled": true,
      "token": "YOUR_BOT_TOKEN",
      "allowFrom": ["YOUR_USER_ID"]
    }
  }
}
```

**5. 邀请机器人**
- OAuth2 → URL Generator
- Scopes：`bot`
- Bot Permissions：`Send Messages`、`Read Message History`
- 打开生成的邀请链接，将机器人加入你的服务器

**6. 运行**

```bash
nanobot gateway
```

</details>

<details>
<summary><b>WhatsApp</b></summary>

需要 **Node.js ≥18**。

**1. 绑定设备**

```bash
nanobot channels login
# 在 WhatsApp 中：设置 → 已关联设备 → 扫码
```

**2. 配置**

```json
{
  "channels": {
    "whatsapp": {
      "enabled": true,
      "allowFrom": ["+1234567890"]
    }
  }
}
```

**3. 运行**（两个终端）

```bash
# 终端 1
nanobot channels login

# 终端 2
nanobot gateway
```

</details>

<details>
<summary><b>飞书</b></summary>

使用 **WebSocket** 长连接，无需公网 IP。

```bash
pip install nanobot-ai[feishu]
```

**1. 创建飞书机器人**
- 打开 [飞书开放平台](https://open.feishu.cn/app)
- 创建应用 → 启用 **机器人** 能力
- **权限**：添加 `im:message`（发送消息）
- **事件**：添加 `im.message.receive_v1`（接收消息）
  - 选择 **长连接** 模式（需先运行 nanobot 建立连接）
- 在「凭证与基础信息」中获取 **App ID** 和 **App Secret**
- 发布应用

**2. 配置**

```json
{
  "channels": {
    "feishu": {
      "enabled": true,
      "appId": "cli_xxx",
      "appSecret": "xxx",
      "encryptKey": "",
      "verificationToken": "",
      "allowFrom": []
    }
  }
}
```

> 长连接模式下 `encryptKey` 和 `verificationToken` 可留空。
> `allowFrom`：留空表示允许所有用户，或填写 `["ou_xxx"]` 限制访问。

**3. 运行**

```bash
nanobot gateway
```

> [!TIP]
> 飞书通过 WebSocket 接收消息，无需配置 Webhook 或公网 IP！

</details>

## ⚙️ 配置

配置文件：`~/.nanobot/config.json`

### 提供商

> [!NOTE]
> Groq 提供免费语音转写（Whisper）。若已配置，Telegram 语音消息将自动转写。

| 提供商 | 用途 | 获取 API Key |
|--------|------|--------------|
| `openrouter` | 大模型（推荐，可访问多种模型） | [openrouter.ai](https://openrouter.ai) |
| `anthropic` | 大模型（Claude 直连） | [console.anthropic.com](https://console.anthropic.com) |
| `openai` | 大模型（GPT 直连） | [platform.openai.com](https://platform.openai.com) |
| `deepseek` | 大模型（DeepSeek 直连） | [platform.deepseek.com](https://platform.deepseek.com) |
| `groq` | 大模型 + **语音转写**（Whisper） | [console.groq.com](https://console.groq.com) |
| `gemini` | 大模型（Gemini 直连） | [aistudio.google.com](https://aistudio.google.com) |
| `aihubmix` | 大模型（API 网关，多模型） | [aihubmix.com](https://aihubmix.com) |
| `dashscope` | 大模型（通义千问） | [dashscope.console.aliyun.com](https://dashscope.console.aliyun.com) |

### 安全

> [!TIP]
> 生产环境建议在配置中设置 `"restrictToWorkspace": true`，将智能体限制在工作区内运行。

| 选项 | 默认值 | 说明 |
|------|--------|------|
| `tools.restrictToWorkspace` | `false` | 为 `true` 时，**所有**智能体工具（Shell、文件读写/编辑、列表）仅限在工作区目录内操作，防止路径穿越和越权访问。 |
| `channels.*.allowFrom` | `[]`（允许所有人） | 用户 ID 白名单。空数组 = 允许所有人；非空 = 仅列出的用户可交互。 |

## CLI 参考

| 命令 | 说明 |
|------|------|
| `nanobot onboard` | 初始化配置与工作区 |
| `nanobot agent -m "..."` | 与智能体对话（单条消息） |
| `nanobot agent` | 交互式对话模式 |
| `nanobot gateway` | 启动网关 |
| `nanobot status` | 查看状态 |
| `nanobot channels login` | 绑定 WhatsApp（扫码） |
| `nanobot channels status` | 查看通道状态 |

<details>
<summary><b>定时任务（Cron）</b></summary>

```bash
# 添加任务
nanobot cron add --name "daily" --message "早上好！" --cron "0 9 * * *"
nanobot cron add --name "hourly" --message "检查状态" --every 3600

# 列出任务
nanobot cron list

# 删除任务
nanobot cron remove <job_id>
```

</details>

## 🐳 Docker

> [!TIP]
> 使用 `-v ~/.nanobot:/root/.nanobot` 可将本地配置目录挂载进容器，配置和工作区在容器重启后仍会保留。

在容器中构建并运行 nanobot：

```bash
# 构建镜像
docker build -t nanobot .

# 初始化配置（仅首次）
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot onboard

# 在宿主机编辑配置，填入 API 密钥
vim ~/.nanobot/config.json

# 运行网关（连接 Telegram/WhatsApp 等）
docker run -v ~/.nanobot:/root/.nanobot -p 18790:18790 nanobot gateway

# 或执行单次命令
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot agent -m "你好！"
docker run -v ~/.nanobot:/root/.nanobot --rm nanobot status
```

## 📁 项目结构

```
nanobot/
├── agent/          # 🧠 核心智能体逻辑
│   ├── loop.py     #    智能体循环（LLM ↔ 工具执行）
│   ├── context.py  #    提示构建
│   ├── memory.py   #    持久化记忆
│   ├── skills.py   #    技能加载
│   ├── subagent.py #    后台任务执行
│   └── tools/      #    内置工具（含 spawn）
├── skills/         # 🎯 内置技能（github、weather、tmux 等）
├── channels/       # 📱 WhatsApp 集成
├── bus/            # 🚌 消息路由
├── cron/           # ⏰ 定时任务
├── heartbeat/      # 💓 主动唤醒
├── providers/      # 🤖 LLM 提供商（OpenRouter 等）
├── session/        # 💬 会话管理
├── config/         # ⚙️ 配置
└── cli/            # 🖥️ 命令行
```

## 🤝 贡献与路线图

欢迎提交 PR！代码库刻意保持精简、可读。🤗

**路线图** — 任选一项 [提交 PR](https://github.com/HKUDS/nanobot/pulls)！

- [x] **语音转写** — 支持 Groq Whisper（Issue #13）
- [ ] **多模态** — 看图、听声（图像、语音、视频）
- [ ] **长期记忆** — 重要上下文持久保存
- [ ] **更强推理** — 多步规划与反思
- [ ] **更多集成** — Discord、Slack、邮件、日历
- [ ] **自我改进** — 从反馈与错误中学习

### 贡献者

<a href="https://github.com/HKUDS/nanobot/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=HKUDS/nanobot&max=100&columns=12" />
</a>

## ⭐ Star 历史

<div align="center">
  <a href="https://star-history.com/#HKUDS/nanobot&Date">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=HKUDS/nanobot&type=Date&theme=dark" />
      <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=HKUDS/nanobot&type=Date" />
      <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=HKUDS/nanobot&type=Date" style="border-radius: 15px; box-shadow: 0 0 30px rgba(0, 217, 255, 0.3);" />
    </picture>
  </a>
</div>

<p align="center">
  <em>感谢访问 ✨ nanobot！</em><br><br>
  <img src="https://visitor-badge.laobi.icu/badge?page_id=HKUDS.nanobot&style=for-the-badge&color=00d4ff" alt="Views">
</p>

<p align="center">
  <sub>nanobot 仅供教育、研究及技术交流使用</sub>
</p>
