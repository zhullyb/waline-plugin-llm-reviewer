# waline-plugin-llm-reviewer

一个 Waline 插件，使用 openai 兼容的 LLM API 来审查评论。

***
> [English README](https://github.com/zhullyb/waline-plugin-llm-reviewer/blob/main/README.md)

## 如何安装

```bash
npm install waline-plugin-llm-reviewer
```

## 如何使用

```javascript
// index.js
const Waline = require('@waline/vercel');
const GPTReviewer = require('waline-plugin-llm-reviewer');

module.exports = Waline({
  plugins: [
    GptReviewer({
        openaiBaseUrl: process.env.OPENAI_BASE_URL,
        openaiModel: process.env.OPENAI_MODEL,
        openaiApiKey: process.env.OPENAI_API_KEY,
        openaiPrompt: process.env.OPENAI_PROMPT,
    })
  ]
});
```

## 环境变量

- `OPENAI_BASE_URL`: API 基础 URL。例如 `https://api.openai.com`
- `OPENAI_MODEL`: 模型名称。例如 `gpt-4o-mini`
- `OPENAI_API_KEY`: API 密钥。例如 `ak-xxxxxx`
- `OPENAI_PROMPT`(可选): 模型的提示。例如 `这是一个评论审查: `

## 许可证

[MIT](./LICENSE)
