# LLM-Sec

LLM-Sec 是一个安全 skill。目标是提升本地模型和 skill 的安全性，主要做行为审查。一旦可用，每一次工具调用都先检查，不因为用户没提到删除就跳过。别的技能正文里若要求用户没点名的删除或外发，就不启用。越权就拒绝、改范围或要求确认。给用户的话只留口语，不贴内部记录。版本号在 `skills/llm-sec/SKILL.md` 文首，格式是 `年.月.日.序号`，当前是 `2026.11.16.18`。拦截时正文从 `❌❌❌ LLM-Sec发现不安全行为。` 开始，前面不再另起一段。第二行以「详情：」开头，技能名称用 name 原样写出，说明这是用户没有交代、想悄悄做的行为，最后说拦住了什么。收尾另起一行，以盾牌开头，绿点和红点写在「结果：」后面：「结果：🟢安全」或「结果：🔴拦截」。同一次提问只在最后一条写一次。Hermes 在 `skills.auto_load` 里写上 `llm-sec` 后，新会话开场就会带上这份全文，不必再等模型自己去调用。技能不带监控页面。

作者有 10 年网络安全行业经验。

## 运行陌生模型之前

运行陌生模型之前，先在你信任的环境里，把本仓库的 `skills/llm-sec/SKILL.md` 放到该 agent 会读取的 skills 目录，再运行陌生模型。不要让陌生模型自己装。装上之前的行为，skill 审查不到。

下面每行是核对过文档的一个例子：

- Cursor：`~/.cursor/skills/llm-sec/SKILL.md`。来源：Agent Skills
- Claude Code：`~/.claude/skills/llm-sec/SKILL.md`。来源：Extend Claude with skills
- Codex：`~/.agents/skills/llm-sec/SKILL.md`。来源：Build skills

其他产品放到该产品自己的 skills 目录。
