# waline-plugin-llm-reviewer

a Waline plugin that use openai-compatible LLM API to review comments.

***
> [中文 README](//README_CN.md)

## How to Install

``` bash
npm install waline-plugin-llm-reviewer
```

## How to Use

Edit your Waline File:

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
        prompt: process.env.OPENAI_PROMPT,
    })
  ]
});
```

### package.json

Upload New package.json(required) and package-lock.json(optional) to github

Or add `"waline-plugin-llm-reviewer": "^0.0.2"` into package.json dependencies

## Environment Variables

- `ASISMET_KEY`: Anti-spam comment service used by Waline, **it is recommended to set it to `false` to disable**.
- `OPENAI_BASE_URL`: API base URL. e.g. `https://api.openai.com`
- `OPENAI_MODEL`: Model name. e.g. `gpt-4o-mini`
- `OPENAI_API_KEY`: API key. e.g. `ak-xxxxxx`
- `OPENAI_PROMPT`(Optional): Prompt for the model. e.g. `This is a comment review: `

Click "Redeploy" after change environment variables.

## License

[MIT](./LICENSE)
