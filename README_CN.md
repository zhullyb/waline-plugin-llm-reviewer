# waline-plugin-llm-reviewer

一个 Waline 插件，使用 openai 兼容的 LLM API 来审查评论。

***
> [English README](/README.md)

## 如何安装

``` bash
npm install waline-plugin-llm-reviewer
```

## 如何使用

编辑Waline文件：

### index.js

``` javascript
const Waline = require('@waline/vercel');
const GPTReviewer = require('waline-plugin-llm-reviewer');

module.exports = Waline({
  plugins: [
    GPTReviewer({
        openaiBaseUrl: process.env.OPENAI_BASE_URL,
        openaiModel: process.env.OPENAI_MODEL,
        openaiApiKey: process.env.OPENAI_API_KEY,
        openaiPrompt: process.env.OPENAI_PROMPT,
    })
  ]
});
```

### package.json

将 `"waline-plugin-llm-reviewer": "latest"` 添加到 package.json 依赖项中。

## 环境变量

- `ASISMET_KEY`: Waline 使用的反垃圾评论服务，**建议设置为 `false` 以禁用**。
- `OPENAI_BASE_URL`: API 基础 URL。例如 `https://api.openai.com`
- `OPENAI_MODEL`: 模型名称。例如 `gpt-4o-mini`
- `OPENAI_API_KEY`: API 密钥。例如 `ak-xxxxxx`
- `OPENAI_PROMPT`(可选): 模型的提示。例如 `这是一个评论审查: `

更改环境变量后点击“重新部署”。

## 许可证

[MIT](./LICENSE)
