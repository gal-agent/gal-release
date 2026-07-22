# GAL 发版仓库

[English](README.md)

**可以放手干活的 LLM agent。** 一个二进制，CLI / GUI / IM 服务三种形态。Linux、macOS、Windows 全平台支持，零安装、内核级安全。

![GAL CLI](image/gal-cli.png)

```bash
# Linux / macOS
./gal init && ./gal chat

# Windows GUI - 双击 galw.exe 即可
```

---

## 为什么选 GAL

agentic loop 早就不是稀罕事了 - 能让 LLM 自主调用工具循环到完成的工具一抓一大把。GAL 的差异在那些工具跳过的地方：**CLI、GUI、IM 一套引擎，Linux / macOS / Windows 一致体验，自带内核级沙箱可以放心地常驻生产环境 - 不需要 Docker，不依赖远端 sandbox，也不靠每一步弹窗确认。**

| 形态 | 二进制 | 安装 |
|------|--------|------|
| 终端 / SSH | `gal` | 拷过去，运行 |
| 桌面 GUI | `galw` | 拷过去，双击 |
| IM / HTTP 服务 | `gal serve` | 拷过去，填上 token，运行 |

### 真机上也敢开

内核级沙箱，三大平台同一套安全模型 - Linux（私有挂载命名空间 + OverlayFS）、macOS（Seatbelt）、Windows（AppContainer）。LLM 在你的项目里能放手干活，无法损坏系统或外传机密。需要装包或重启服务？`/sudo <msg>` 临时放行一轮，下一轮自动恢复。

### 长会话也能扛住

由 LLM 自己决定哪些压缩、哪些保留 - 长会话保持连贯，不会被强行截断，也不会无声丢失早期内容。单次会话可支撑数万轮 agent 交互，当前轮永远受保护。

### 自我扩展

- **Skills** - 把 `SKILL.md` + 脚本放进一个目录，LLM 自动识别，脚本即工具。
- **MCP** - 接任意 MCP 服务器，工具和资源自动出现，懒加载。

---

## 下载

每个 [Release](https://github.com/ai-agent-home/gal-release/releases) 包含分平台压缩包。压缩包内的二进制是干净名称（`gal` / `galw`），平台信息只体现在压缩包文件名上。

| 平台 | CLI（`gal`） | GUI（`galw`） |
|------|-------------|--------------|
| Linux amd64 | `gal-linux-amd64.tar.gz` | `galw-linux-amd64.tar.gz` |
| macOS amd64（Intel） | `gal-darwin-amd64.tar.gz` | `galw-darwin-amd64.zip` |
| macOS arm64（Apple Silicon） | `gal-darwin-arm64.tar.gz` | `galw-darwin-arm64.zip` |
| Windows amd64 | `gal-windows-amd64.zip` | `galw-windows-amd64.zip` |

### 快速开始

```bash
# Linux / macOS
tar xzf gal-linux-amd64.tar.gz
chmod +x gal
./gal init && ./gal chat

# Windows
# 解压 gal-windows-amd64.zip，双击 gal.exe
# GUI 版：双击 galw.exe
```

### 校验完整性

每个版本附带 `checksums.txt`，下载后可校验：

```bash
sha256sum -c checksums.txt --ignore-missing
```

---

## 问题与反馈

- 🐛 **Bug 报告**：[提交 Issue](https://github.com/ai-agent-home/gal-release/issues/new?labels=bug)
- ✨ **功能建议**：[提交 Issue](https://github.com/ai-agent-home/gal-release/issues/new?labels=enhancement)
- 💬 **讨论 / 问答**：[发起讨论](https://github.com/ai-agent-home/gal-release/discussions)

也可以通过[官网反馈页](https://agent-home.ai/feedback.html)提交反馈。

---

## 链接

- [官方网站](https://agent-home.ai) - 文档、下载页、反馈
- [所有版本](https://github.com/ai-agent-home/gal-release/releases)
