<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100:0f3460&height=180&section=header&text=Leonis%20AI&fontSize=64&fontColor=ffffff&fontAlignY=32&desc=114%20个模型%20·%20Claude%20/%20GPT%20/%20Gemini%20/%20Grok%20国内直连&descAlignY=54&descSize=16" width="100%" />

### 一个 Key，114 个模型 —— Claude · OpenAI · Gemini · Grok

**AI API 中转网关** — 国内直连、OpenAI 与 Anthropic 双协议兼容、按 Token 实时计费

[![官网](https://img.shields.io/badge/官网-ai.svtun.cn-1a73e8?style=for-the-badge&logo=googlechrome&logoColor=white)](https://ai.svtun.cn)
[![Claude Code](https://img.shields.io/badge/Claude_Code-原生支持-D97757?style=for-the-badge&logo=anthropic&logoColor=white)](https://github.com/leonis-ai/claude-code-guide)
[![Codex](https://img.shields.io/badge/Codex_CLI-原生支持-412991?style=for-the-badge&logo=openai&logoColor=white)](https://github.com/leonis-ai/ai-client-configs)

![Anthropic](https://img.shields.io/badge/Anthropic-Claude_Opus_5-D97757?style=flat-square&logo=anthropic&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--5.6-412991?style=flat-square&logo=openai&logoColor=white)
![Gemini](https://img.shields.io/badge/Google-Gemini_3.6-8E7CFF?style=flat-square&logo=google&logoColor=white)
![xAI](https://img.shields.io/badge/xAI-Grok_4.5-000000?style=flat-square&logo=x&logoColor=white)
![Models](https://img.shields.io/badge/模型总数-114-1a73e8?style=flat-square)
![Protocol](https://img.shields.io/badge/协议-OpenAI_%2B_Anthropic-2ea44f?style=flat-square)

</div>

---

## 这是什么

**Leonis AI** 是一个 AI API 中转网关（AI API Gateway / LLM Proxy），把 Claude、OpenAI、Google Gemini、xAI Grok 的 **114 个模型**聚合到**同一个 Base URL + 同一个 Key** 下。

原本你需要四个平台的账号、几张外币信用卡、四套 SDK；现在改一行 `BASE_URL` 就够了。

```diff
- ANTHROPIC_BASE_URL=https://api.anthropic.com
+ ANTHROPIC_BASE_URL=https://ai.svtun.cn/api
```

<div align="center">

| | 官方直连 | Leonis AI 网关 |
|:---|:---:|:---:|
| 网络环境 | 需自备国际网络 | **国内直连** |
| 支付方式 | 外币信用卡 | **支付宝 / 微信** |
| 账号数量 | 每家一个 | **一个 Key 全平台** |
| 计费方式 | 各平台独立账单 | **统一余额，实时可查** |
| Claude Opus | 需 Max 订阅（$100/月起） | **按量付费，用多少扣多少** |
| 用量窗口 | Pro/Max 有 5h 窗口限制 | **无窗口限制** |

</div>

---

## 快速开始

### Claude Code

```bash
export ANTHROPIC_BASE_URL="https://ai.svtun.cn/api"
export ANTHROPIC_AUTH_TOKEN="sk-your-key-here"

claude
```

### Codex CLI

```toml
# ~/.codex/config.toml
model_provider = "leonis"

[model_providers.leonis]
name = "Leonis AI"
base_url = "https://ai.svtun.cn/api/v1"
wire_api = "responses"
env_key = "LEONIS_API_KEY"
```

### OpenAI SDK（Python）

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://ai.svtun.cn/api/v1",
    api_key="sk-your-key-here",
)

resp = client.chat.completions.create(
    model="gpt-5.6-sol",
    messages=[{"role": "user", "content": "Hello"}],
)
```

### Anthropic SDK（Python）

```python
from anthropic import Anthropic

client = Anthropic(
    base_url="https://ai.svtun.cn/api",
    auth_token="sk-your-key-here",
)

msg = client.messages.create(
    model="claude-opus-5",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Hello"}],
)
```

> 📖 更多客户端（Cursor / Cline / Roo Code / Cherry Studio / ChatBox / NextChat / OpenWebUI）配置见
> **[ai-client-configs](https://github.com/leonis-ai/ai-client-configs)**

---

## 支持的模型 — 共 114 个

<table>
<tr>
<th align="left">⭐ Anthropic <sub>10</sub></th>
<th align="left">OpenAI <sub>13</sub></th>
<th align="left">Google Gemini <sub>78</sub></th>
<th align="left">xAI Grok <sub>13</sub></th>
</tr>
<tr valign="top"><td>

**编码首选**

`claude-opus-5`
`claude-opus-4-8`
`claude-opus-4-7`
`claude-sonnet-5`
`claude-sonnet-4-6`
`claude-haiku-4-5`
`claude-fable-5`

</td><td>

**Codex 原生**

`gpt-5.6-sol`
`gpt-5.6`
`gpt-5.6-terra`
`gpt-5.5`
`gpt-5.4-mini`
`gpt-5.3-codex-spark`
`gpt-image-2`

</td><td>

**覆盖最全**

`gemini-3.6-flash`
`gemini-3.1-pro-preview`
`gemini-3.5-flash-thinking`
`gemini-3-pro-image-4k`
`nano-banana-pro`
`imagen-4.0-ultra`
`gemini-embedding-001`

</td><td>

**含图像视频**

`grok-4.5`
`grok-4.3`
`grok-composer-2.5-fast`
`grok-build-0.1`
`grok-imagine-image`
`grok-imagine-video`

</td></tr>
</table>

> 📋 **[查看全部 114 个模型 →](https://leonis-ai.github.io/models.html)** 支持搜索过滤，点击即复制模型名

**Gemini 变体后缀速查**：`-thinking` 开思考链 ｜ `-nothinking` 关思考链（最省） ｜ `-search` 内置联网 ｜ `-image` 出图 ｜ `-2k`/`-4k` 输出分辨率 ｜ `-latest` 自动跟随最新版

### 兼容端点

| 端点 | 协议 | 典型客户端 |
|---|---|---|
| `/v1/messages` | Anthropic Messages | Claude Code、Anthropic SDK、Cline |
| `/v1/chat/completions` | OpenAI Chat | 绝大多数第三方客户端；**Gemini 与 Grok 走这个** |
| `/v1/responses` | OpenAI Responses | Codex CLI、Codex Desktop |

---

## 核心能力

- **🔀 多平台聚合** — Claude / OpenAI / Gemini / Grok 共 114 个模型，一个 Key 全通
- **🎨 图像生成** — Nano Banana Pro、Imagen 4.0 Ultra、gpt-image-2、Grok Imagine 全都在
- **⚡ Prompt 缓存** — 完整支持 Anthropic Prompt Caching，长代码长文档重复读取近乎零成本
- **📊 用量可追溯** — 每一次请求、每一笔 Token 消耗、每一分钱都有明细，随时可查
- **🔁 多通道容灾** — 多上游节点自动调度，单点故障自动切换
- **🎚️ 分组倍率** — 按需选择通道，经济通道与高速通道自由切换
- **🌐 国内直连** — 无需额外网络配置

---

## 项目导航

<table>
<tr>
<td width="50%">

### 📘 [claude-code-guide](https://github.com/leonis-ai/claude-code-guide)
**Claude Code 中文完全指南**

安装、配置、第三方 API 接入、成本优化、常见报错排查。从零到熟练的完整路径。

</td>
<td width="50%">

### 🟣 [codex-cli-guide](https://github.com/leonis-ai/codex-cli-guide)
**Codex CLI 完全配置手册**

`config.toml` 全字段详解、多 Provider 配置、审批与沙箱、MCP、`AGENTS.md`。

</td>
</tr>
<tr>
<td width="50%">

### ✨ [gemini-api-guide](https://github.com/leonis-ai/gemini-api-guide)
**Gemini API 中文配置手册**

78 个模型详解、命名规则拆解、thinking / search 变体、Nano Banana 与 Imagen 生图。

</td>
<td width="50%">

### 🔀 [cc-switch-guide](https://github.com/leonis-ai/cc-switch-guide)
**多配置一键切换**

用 cc-switch 管理 Claude Code 与 Codex 的多套供应商配置，点一下就切换。

</td>
</tr>
<tr>
<td width="50%">

### ⚡ [awesome-ai-api-gateway](https://github.com/leonis-ai/awesome-ai-api-gateway)
**AI 网关与中转生态精选**

开源网关、协议转换、路由调度、可观测性 —— 一份持续更新的 awesome 清单。

</td>
<td width="50%">

### 💰 [ai-api-pricing](https://github.com/leonis-ai/ai-api-pricing)
**成本计算与缓存经济学**

为什么 Claude Code 的账单和你想的不一样，附可运行的成本计算器。

</td>
</tr>
<tr>
<td width="50%">

### 🔧 [ai-client-configs](https://github.com/leonis-ai/ai-client-configs)
**客户端对接配置合集**

20+ 主流 AI 客户端的 Base URL 配置模板，复制即用。

</td>
<td width="50%">

### 📋 [全部 114 个模型](https://leonis-ai.github.io/models.html)
**在线可搜索模型清单**

Claude / GPT / Gemini / Grok 全系模型名，支持关键词过滤，点击即复制。

</td>
</tr>
</table>

---

## 常见问题

<details>
<summary><b>和 one-api / new-api / sub2api 这类项目是什么关系？</b></summary>

<br>

那些是**自建网关的开源软件**，你需要自己部署、自己找上游、自己维护。

Leonis AI 是**已经部署好的托管服务** —— 你不用管服务器、不用管上游账号、不用管故障切换，拿 Key 直接用。

如果你想自建，`awesome-ai-api-gateway` 里整理了全部可选方案。

</details>

<details>
<summary><b>会不会封我的账号？</b></summary>

<br>

不会。走的是 API 网关，全程不接触你的 Claude / OpenAI 账号，你甚至不需要有这些账号。

</details>

<details>
<summary><b>支持 Prompt 缓存吗？对 Claude Code 影响大吗？</b></summary>

<br>

完整支持。这一点对 Claude Code 尤其关键 —— Claude Code 每轮对话都会重发项目上下文，实测缓存读取可占总 Token 量的 67%~86%，有缓存和没缓存的成本能差好几倍。

</details>

<details>
<summary><b>怎么控制成本？</b></summary>

<br>

三条实操建议：

1. **日常主用 Sonnet，卡关再切 Opus** — Opus 单价约为 Sonnet 的 5 倍
2. **善用 `/clear`** — Claude Code 上下文越长，每轮重发的 Token 越多
3. **配置 `.claudeignore`** — 把 `node_modules`、构建产物、大型资源文件排除掉

详见 [claude-code-guide 的成本优化章节](https://github.com/leonis-ai/claude-code-guide#成本优化)。

</details>

---

<div align="center">

### 🚀 [立即开始 → ai.svtun.cn](https://ai.svtun.cn)

<sub>

**关键词** · AI 中转 · API 中转 · AI 网关 · AI API Gateway · LLM Proxy · Claude 中转 · Claude API · Claude Opus 5
Claude Code 中转 · OpenAI 反代 · GPT 中转 · GPT-5.6 · Codex CLI · Anthropic API
Gemini 中转 · Gemini API · 谷歌 Gemini · Nano Banana Pro · Imagen 4.0 · Grok API · Grok 4.5
国内直连 · 大模型 API 聚合 · AI 生图 API

</sub>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f3460,50:16213e,100:1a1a2e&height=100&section=footer" width="100%" />

</div>
