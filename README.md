<p align="center">
  <a href="https://github.com/runapi-ai/qwen">
    <h3 align="center">Qwen API Skill for RunAPI</h3>
  </a>
</p>

<p align="center">
  Configure OpenAI-compatible clients to use Qwen text models on RunAPI.
</p>

<p align="center">
  <a href="https://runapi.ai/models/qwen"><strong>Model Reference</strong></a> | <a href="https://github.com/runapi-ai/qwen"><strong>Skill Repo</strong></a> | <a href="https://runapi.ai/models"><strong>All Models</strong></a>
</p>

<div align="center">

[![skills.sh](https://www.skills.sh/b/runapi-ai/qwen)](https://www.skills.sh/runapi-ai/qwen/qwen)
[![ClawHub](https://img.shields.io/badge/ClawHub-runapi--qwen-111827)](https://clawhub.ai/runapi-ai/runapi-qwen)
[![License](https://img.shields.io/github/license/runapi-ai/qwen)](https://github.com/runapi-ai/qwen/blob/main/LICENSE)

</div>
<br/>

Call Qwen text models through RunAPI with the official OpenAI SDK or any
OpenAI-compatible client. Point clients at `https://runapi.ai/v1`, send
`qwen3-next-80b-a3b-instruct`, and pay through one RunAPI balance. This skill
teaches Claude Code, Codex, Gemini CLI, Cursor, and 50+ agents how to wire Qwen
text requests through RunAPI.

The canonical agent file is `skills/qwen/SKILL.md`.

## Install the skill

```bash
npx skills add runapi-ai/qwen -g
```

Or paste this prompt to your AI agent:

```text
Install the qwen skill for me:

1. Clone https://github.com/runapi-ai/qwen
2. Copy the skills/qwen/ directory into your
   user-level skills directory (e.g. ~/.claude/skills/
   for Claude Code, ~/.codex/skills/ for Codex).
3. Verify that SKILL.md is present.
4. Confirm the install path when done.
```

## Use Qwen on RunAPI

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_RUNAPI_TOKEN",
    base_url="https://runapi.ai/v1",
)

response = client.chat.completions.create(
    model="qwen3-next-80b-a3b-instruct",
    messages=[{"role": "user", "content": "Hello, Qwen!"}],
)
print(response.choices[0].message.content)
```

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: "YOUR_RUNAPI_TOKEN",
  baseURL: "https://runapi.ai/v1",
});

const response = await client.chat.completions.create({
  model: "qwen3-next-80b-a3b-instruct",
  messages: [{ role: "user", content: "Hello, Qwen!" }],
});
console.log(response.choices[0].message.content);
```

Get a RunAPI API Key at <https://runapi.ai/api_keys>.

## Supported Qwen text models

| Model ID | Notes |
|---|---|
| `qwen3-next-80b-a3b-instruct` | Qwen text chat and instruction-following workloads |

## Routing

- Qwen API on RunAPI: <https://runapi.ai/models/qwen>
- Provider page: <https://runapi.ai/providers/alibaba>
- Browse the full RunAPI catalog: <https://runapi.ai/models>
- Skill repository: <https://github.com/runapi-ai/qwen>

## Agent rules

- Keep API keys in `OPENAI_API_KEY` or your secret manager; never inline them in
  commits or shell history.
- Stream long responses (`stream: true`) so the agent can release the
  terminal/IO loop early.
- This skill is for Qwen text models. Use the Qwen 2 skill for image generation.
- For pricing, rate-limit, and commercial-usage answers, link to
  <https://runapi.ai/models/qwen> rather than this README.

## License

Licensed under the Apache License, Version 2.0.
