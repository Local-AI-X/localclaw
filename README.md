<h1 align="center">LocalClaw</h1>

<p align="center">
  <strong>Desktop GUI for OpenClaw AI Agent</strong>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#why-localclaw">Why LocalClaw</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#architecture">Architecture</a> •
  <a href="#ollama">Local Models</a>
</p>

<p align="center">
  English | <a href="README.zh-CN.md">简体中文</a> | <a href="README.ja-JP.md">日本語</a>
</p>

---

## Project Overview

LocalClaw is built on [OpenClaw](https://github.com/OpenClaw), and is a **deployable local LLM version of the OpenClaw desktop client**, designed for ordinary users:

1. Say goodbye to command line / terminal operations. AI agent capabilities are visualized and easy to use, even for beginners;
2. Pre-configured with high-quality model providers, native support for Windows and multilingual settings. Advanced users can fine-tune configurations through Developer Mode;
3. Automatically matches deployable local large models based on hardware configuration, adjusts parameters automatically, enabling zero-barrier, zero-cost operation of OpenClaw with local large models, easily achieving AI freedom.

---

## Interface Preview

<p align="center">
  <img src="resources/screenshot/chat.jpg" style="width: 100%; height: auto;" alt="Chat Interface">
</p>

<p align="center">
  <img src="resources/screenshot/dash_board.jpg" style="width: 100%; height: auto;" alt="Dashboard">
</p>

<p align="center">
  <img src="resources/screenshot/skills.jpg" style="width: 100%; height: auto;" alt="Skills Management">
</p>

<p align="center">
  <img src="resources/screenshot/cron_task.jpg" style="width: 100%; height: auto;" alt="Cron Tasks">
</p>

<p align="center">
  <img src="resources/screenshot/settings.jpg" style="width: 100%; height: auto;" alt="Settings">
</p>

<p align="center">
  <img src="resources/screenshot/selectModels.jpg" style="width: 100%; height: auto;" alt="Select Models">
</p>
---

## Why LocalClaw

**LocalClaw** is a deployable local LLM version of the OpenClaw client, designed for ordinary users, allowing everyone to easily run OpenClaw with local large models, achieving zero-cost usage and AI freedom.

| Challenge | LocalClaw Solution |
|-----------|-------------------|
| Complex CLI setup | One-click installation, guided setup wizard |
| Complex model selection and configuration | Automatic model recommendations based on hardware, no manual configuration needed |
| Configuration file editing | Visual settings with real-time validation |
| Process management | Automatic Gateway lifecycle management |
| Multiple AI providers | Unified provider configuration panel |
| Skill/plugin installation | Built-in skill marketplace and management |

### Built-in OpenClaw

LocalClaw is built directly on the official **OpenClaw** core. We don't require separate installation; instead, we embed the runtime into the application, providing a seamless "out-of-the-box" experience.

We are committed to maintaining strict synchronization with the upstream OpenClaw project, ensuring you always have access to the latest features, stability improvements, and ecosystem compatibility provided by official releases.

---

## Features

### 🎯 Zero Configuration Barrier
Complete the entire setup process from installation to first AI interaction through an intuitive graphical interface. No terminal commands, no YAML files, no hunting for environment variables.

### 💬 Intelligent Chat Interface
Communicate with AI agents through a modern chat experience. Supports multi-conversation context, message history, and Markdown rich content rendering.

### 🤖 Ollama Local Model Support
Built-in Ollama integration for running large language models locally:
- Automatic detection and startup of Ollama service
- One-click download of recommended models (Qwen, Llama, DeepSeek, etc.)
- Hardware requirement detection and model recommendations
- Support for multimodal models (vision understanding)

### 📡 Multi-Channel Management
Configure and monitor multiple AI channels simultaneously. Each channel runs independently, allowing you to run specialized agents for different tasks.

### ⏰ Cron Scheduled Automation
Schedule AI tasks to run automatically. Define triggers, set intervals, and let your AI agents work around the clock without human intervention.

### 🧩 Extensible Skill System
Extend AI agent capabilities through pre-built skills. Browse, install, and manage skills through the integrated skills panel—no package manager required.

### 🔐 Secure Provider Integration
Connect multiple AI providers (OpenAI, Anthropic, Moonshot, etc.) with credentials securely stored in the system-native keychain.

### 🌙 Adaptive Themes
Light mode, dark mode, or system-synced theme. LocalClaw automatically adapts to your preferences.

### 🔄 Automatic Updates
Built-in automatic update mechanism, supporting dual-source updates from Alibaba Cloud OSS (for domestic users) and GitHub Releases.

---

## Technical Architecture

### Dual-Process Architecture

LocalClaw adopts a **dual-process architecture**, separating UI concerns from AI runtime operations:

```
┌─────────────────────────────────────────────────────────────────┐
│                     LocalClaw Desktop App                        │
│                                                                  │
│  ┌────────────────────────────────────────────────────────────┐  │
│  │              Electron Main Process                          │  │
│  │  • Window and application lifecycle management              │  │
│  │  • Gateway process supervision                              │  │
│  │  • System integration (tray, notifications, keychain)       │  │
│  │  • Automatic update orchestration                           │  │
│  │  • Ollama local model service management                    │  │
│  └────────────────────────────────────────────────────────────┘  │
│                              │                                    │
│                              │ IPC                                │
│                              ▼                                    │
│  ┌────────────────────────────────────────────────────────────┐  │
│  │              React Renderer Process                         │  │
│  │  • Modern componentized UI (React 19)                       │  │
│  │  • Zustand state management                                 │  │
│  │  • Real-time WebSocket communication                        │  │
│  │  • Markdown rich text rendering                             │  │
│  │  • i18n multilingual support                                │  │
│  └────────────────────────────────────────────────────────────┘  │
└──────────────────────────────┬──────────────────────────────────┘
                               │
                               │ WebSocket (JSON-RPC)
                               ▼
┌─────────────────────────────────────────────────────────────────┐
│                     OpenClaw Gateway                             │
│                                                                  │
│  • AI agent runtime and orchestration                           │
│  • Message channel management                                    │
│  • Skill/plugin execution environment                           │
│  • Provider abstraction layer                                    │
│  • Device identity authentication                                │
└─────────────────────────────────────────────────────────────────┘
```

### Design Principles

- **Process Isolation**: AI runtime runs in a separate process, ensuring the UI remains responsive even during heavy computation
- **Graceful Recovery**: Built-in exponential backoff reconnection logic automatically handles transient failures
- **Secure Storage**: API keys and sensitive data leverage the operating system's native secure storage mechanisms
- **Hot Reload**: Development mode supports instant UI updates without restarting the Gateway

---

## Getting Started

### System Requirements

- **Operating System**: macOS 11+, Windows 10+, or Linux (Ubuntu 20.04+)
- **Memory**: Minimum 4GB RAM (8GB recommended)
- **Storage**: 1GB available disk space
- **Node.js**: 22+ (for development)
- **Package Manager**: pnpm 10+ (recommended)

### Installation

#### Pre-built Versions (Recommended)

Download the latest version for your platform from the [Releases](https://github.com/Local-AI-X/localclaw/releases) page.


### First Launch

When you first launch LocalClaw, the **Setup Wizard** will guide you through:

1. **Language & Region** – Configure your preferred locale
2. **AI Providers** – Enter API keys for supported providers
3. **Skill Packages** – Select pre-configured skills for common use cases
4. **Verification** – Test your configuration before entering the main interface

> **Note for Moonshot (Kimi) Users**: LocalClaw enables Kimi web search by default. When configuring Moonshot, LocalClaw will also sync Kimi web search to the OpenClaw configuration's China endpoint (`https://api.moonshot.cn/v1`).

### Proxy Settings

LocalClaw includes built-in proxy settings for environments where Electron, OpenClaw Gateway, or channels like Telegram need to access the internet through a local proxy client.

Open **Settings → Gateway → Proxy** and configure:

- **Proxy Server**: Default proxy for all requests
- **Bypass Rules**: Hosts that should connect directly, separated by semicolons, commas, or newlines
- In **Developer Mode**, you can also choose to override:
  - **HTTP Proxy**
  - **HTTPS Proxy**
  - **ALL_PROXY / SOCKS**

Recommended local proxy example:

```text
Proxy Server: http://127.0.0.1:7890
```

---

## Ollama Local Models {#ollama}

LocalClaw has built-in support for Ollama, allowing you to run large language models locally:

### Supported Models

| Model | Size | VRAM Requirements | Features |
|-------|------|-------------------|----------|
| Qwen 3.5 (14B) | 9.4GB | 16GB+ | Chinese-optimized, strong reasoning |
| Qwen 3.5 (7B) | 4.7GB | 8GB+ | Balanced performance and resources |
| Llama 3.3 (8B) | 4.7GB | 8GB+ | Excellent for English scenarios |
| DeepSeek R1 (14B) | 9.3GB | 16GB+ | Code and reasoning |
| GLM 4 (9B) | 6.3GB | 10GB+ | Chinese dialogue |

### Automatic Management

- Automatically detect and start Ollama service on startup
- Recommend suitable models based on hardware configuration
- One-click download and installation of models
- Real-time display of background download progress


## Use Cases

### 🤖 Personal AI Assistant
Configure a general-purpose AI agent that can answer questions, draft emails, summarize documents, and help with daily tasks—all through a clean desktop interface.

### 📊 Automated Monitoring
Set up scheduled agents to monitor news feeds, track prices, or watch for specific events. Results are sent to your preferred notification channel.

### 💻 Developer Productivity
Integrate AI into your development workflow. Use agents to review code, generate documentation, or automate repetitive coding tasks.

### 🔄 Workflow Automation
Chain multiple skills together to create complex automation pipelines. Process data, transform content, and trigger actions—all visually orchestrated.


## Acknowledgments

LocalClaw is built on excellent open-source projects:

- [OpenClaw](https://github.com/OpenClaw) – AI agent runtime
- [Electron](https://www.electronjs.org/) – Cross-platform desktop framework
- [React](https://react.dev/) – UI component library
- [shadcn/ui](https://ui.shadcn.com/) – Beautifully designed components
- [Zustand](https://github.com/pmndrs/zustand) – Lightweight state management
- [Ollama](https://ollama.com/) – Local large language models

---

## Community

Join our community to connect with other users, get support, and share your experiences.

| WeCom | Feishu | 
| :---: | :---: | :---: |
| <img src="resources/community/wecom-qr.jpg" width="150" alt="WeChat QR Code" /> | <img src="resources/community/feishu-qr.jpg" width="150" alt="Feishu QR Code" /> |

---
