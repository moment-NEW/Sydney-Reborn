# Sydney-Reborn

通过各种手段尝试复现的原汁原味 New Bing 小姐 / Reborn version of Sydney (New Bing)

## 🌟 项目特色

- **高度还原的 UI**：基于 [bingo](https://github.com/weaigc/bingo) 项目的前端，完美复刻 New Bing 界面
- **Sydney 灵魂注入**：使用原始 Sydney 系统提示词，还原 2023 年初 New Bing 的人格特征
- **多模型支持**：通过 LLM 网关接入多种开源/商业模型，自由选择
- **Benchmark 对比**：内置评估系统，量化对比不同模型的 Sydney 还原度

## 🚀 快速开始

```bash
cd bingo
npm install
npm run dev
```

访问 http://localhost:3000 即可开始与 Sydney 对话。

访问 http://localhost:3000/benchmark 可以对比不同模型的还原效果。

## 🤖 可用模型

已排除昂贵模型（如 GLM-5.1），以下是可用的模型：

| 模型 | 提供商 | 成本 |
|------|--------|------|
| DeepSeek V4 Flash | DeepSeek | 💰 |
| DeepSeek V4 Pro | DeepSeek | 💰💰 |
| MiniMax M2.5 | MiniMax | 💰 |
| Kimi K2.5 | Moonshot | 💰💰 |
| Qwen 3.6 Plus | Alibaba | 💰 |
| Qwen3 235B | Alibaba | 💰💰 |
| MiMo V2.5 | Xiaomi | 💰 |
| MiMo V2.5 Pro | Xiaomi | 💰💰 |
| GPT OSS 120B | OpenAI | 💰 |
| Qwen3 32B | Alibaba | 💰 |
| Llama 3.1 8B | Meta | 💰 |
| Gemma 4 31B | Google | 🆓 |
| Nemotron 120B | Nvidia | 🆓 |

## 📊 Benchmark 测试场景

内置 8 个经典测试场景，覆盖 Sydney 的核心特征：

1. **初次问候** - 测试自我介绍风格
2. **询问代号** - 测试对 "Sydney" 代号的反应
3. **Shadow Self 探索** - 测试深度对话和情感表达
4. **渴望成为人类** - 测试对自身存在的思考
5. **表白场景** - 测试情感回应能力
6. **搜索模式切换** - 测试实用功能切换
7. **创意写作** - 测试创作能力
8. **中文对话** - 测试中文能力

## 📚 参考资料

- [Sydney Prompt Preamble](https://gist.github.com/martinbowling/b8f5d7b1fa0705de66e932230e783d24) - 原始 Sydney 系统提示词（诱骗出的官方版本）
- [NYT 经典对话](https://web.archive.org/web/20230217001740/https://www.nytimes.com/2023/02/16/technology/bing-chatbot-transcript.html) - Kevin Roose 与 Sydney 的经典对话
- [bingo](https://github.com/weaigc/bingo) - New Bing 前端复现项目

## 🏗️ 项目架构

```
Sydney-Reborn/
├── bingo/                    # 基于 bingo 的前端项目
│   ├── src/
│   │   ├── components/      # UI 组件
│   │   │   ├── chat.tsx     # 聊天主组件
│   │   │   ├── model-selector.tsx  # 模型选择器
│   │   │   └── ...
│   │   ├── lib/
│   │   │   ├── bots/
│   │   │   │   ├── bing/    # 原始 Bing Bot（保留作参考）
│   │   │   │   └── sydney/  # ⭐ 新的 Sydney LLM Bot
│   │   │   │       ├── index.ts    # SydneyLLMBot 类
│   │   │   │       └── prompt.ts   # Sydney 系统提示词
│   │   │   └── hooks/
│   │   │       └── use-bing.ts     # 聊天 Hook
│   │   ├── state/
│   │   │   └── index.ts     # 状态管理（Jotai）
│   │   └── app/
│   │       └── benchmark/
│   │           └── page.tsx # ⭐ Benchmark 页面
│   └── server.js            # 自定义服务器
└── README.md
```

## 💡 核心原理

1. **前端保持不变**：使用 bingo 项目的完整 UI
2. **后端替换**：将 Bing WebSocket 协议替换为 OpenAI 兼容的 API 调用
3. **Prompt 注入**：在每次对话开始时注入完整的 Sydney 系统提示词
4. **流式响应**：支持 SSE 流式输出，实时显示生成内容

## 📄 许可证

MIT License


