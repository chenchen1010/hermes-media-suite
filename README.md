

# hermes-media-suite

一台109一年的云服务器 + Hermes，跑起两个真能干活的 agent：

1. **音视频转录整理**：丢一个链接/文件给它，还你一份提纯过的中文文稿（不是三句话摘要）。
   整理标准的思路来自生财有术亦仁分享的「小D」agent，在此致谢；本仓库是社区重写与升级版。
2. **四平台社媒调研**：小红书、抖音、微信公众号、微信视频号——丢链接直取内容，
   关键词跨平台搜索，挖评论区，拆对标账号。

两个 agent 拼起来是一条"收藏处理流水线"：平时随手扔进群里的链接
（公众号文章、抖音视频、小红书笔记、视频号），agent 拉回内容、转录整理、归档——
把"收藏了从没看过"变成"收藏了就有输出"。

它们跑在服务器上，不绑你的电脑。电脑关机，agent 照样干活；
在微信或者飞书里发条消息就能使唤。

## 仓库结构

```
INSTALL_PROMPT.md             一键安装提示词：复制丢给 Codex/Claude Code，替你装完整套
mcp/tikhub_xhs_mcp.py         TikHub 四平台采集 MCP（零依赖，20 个工具，主链路真实调用验证过）
profiles/media-transcriber.md 转录整理 agent 的指令
profiles/social-research.md   四平台社媒调研 agent 的指令
docs/deploy-cheap-server.md   从买服务器到跑通的完整教程
```

## 快速开始

打开 [INSTALL_PROMPT.md](INSTALL_PROMPT.md)，把前置资料备齐、提示词里的【】填好，
丢给你的 Codex / Claude Code，它替你装完整套。

## 把账算明白

| 项目 | 花费 |
| --- | --- |
| 服务器 | 一百元上下一年（入门轻量云主机） |
| 大模型 | 自己的 key，用多少花多少（deepseek 性价比高；有 ChatGPT 会员也可接入共享额度） |
| TikHub | 按调用计费，只在用社媒调研时产生；响应带 24h 免费 cache_url。注册入口：[user.tikhub.io/register?ref=EJ7Ka9h8](https://user.tikhub.io/register?ref=EJ7Ka9h8)（带我的推荐码，不加价，介意可去掉 ref 参数） |

软件本身全部免费开源。

## 为什么自己写 MCP，不用 TikHub 官方的？

TikHub 有官方 MCP 生态（托管版 mcp.tikhub.io、`pip install tikhub-mcp` 自托管版、桌面打包代理），
服务器上不是不能跑。没用它的原因是不合身：官方版本面向全平台通用（13+ 平台、上千个端点的家底），
工具一多，agent 选起来又慢又容易错。这里是为「收藏处理 + 社媒调研」场景策展的 20 个工具——
中文描述、贴分享口令就能用、图文视频自动回退、花钱纪律写进指令——而且零依赖单文件，
你花五分钟就能把代码审完。需要更多平台的，用官方的：github.com/TikHub。

## 致谢

- [Hermes](https://github.com/NousResearch/hermes-agent) —— 底座 agent 框架（本仓库与 Nous Research 无关联，仅为使用者）
- 生财有术 · 亦仁的「小D」转录整理 agent —— 分享式提纯的整理标准由它启发
- [TikHub](https://tikhub.io) —— 四平台社媒公开数据 API（小红书/抖音/公众号/视频号）

## 想继续交流？

这套开源方案就是全部，照着装就能用，没有任何保留。

如果你安装完后，针对更多的玩法想要有人一起交流，我组了一个付费交流群，Hermes ai共学社（¥199一年）：我会持续分享新的 workflows / skills；如果你在过程中卡住了，也可以来群里询问。懒得自己动手的，我也可以帮你装。

有意可加微信 BurningChen1010，备注「共学社」。

## License

MIT
