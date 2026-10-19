# Tools around Seedance 2.5 (BytePlus only)

Researched 2026-10-06 by subagent. Medium confidence: web search summaries, no code read, nothing installed. Re-check before relying.

Default path is the ModelArk API in SKILL.md. Do not install or add any of the below without Tom's approval.

| Tool | What it gives | Cons |
|---|---|---|
| `sd25-pe` (official BytePlus prompt optimizer) | Vendor rulebook for 2.5. Turns raw text and references into one prompt. Never calls the API. Install (only with Tom's approval): `npx --yes skills@latest add "https://arkdocs-en.tos-ap-southeast-1.volces.com/skills/" --skill sd25-pe --yes`, then `/sd25-pe <prompt>`. | Runs `npx skills@latest update sd25-pe -y` each session (network code). The BytePlus URL gave 404 on 2026-10-06. A third-party mirror was read: `openstory-so/openstory` `.agents/skills/sd25-pe/SKILL.md` v0.1.1 |

Third-party skills that say "720p max, 15 s" describe Seedance 2.0. Ignore those limits.
