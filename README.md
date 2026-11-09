# Personal Skills

A personal collection of reusable skills for agent tools. Research paper reading, writing, and polishing are the first category.

Repository maintenance conventions are in [AGENTS.md](AGENTS.md).

## Research paper skills

| Skill | Use it to |
| --- | --- |
| [`research-paper-reading`](research-paper-reading/SKILL.md) | Explain a paper from its original figures, captions, and experiments, and cross-check claims against released code. |
| [`research-paper-writing`](research-paper-writing/SKILL.md) | Draft and revise paper sections, organize the story, and align claims with evidence. |
| [`research-paper-polishing`](research-paper-polishing/SKILL.md) | Improve the clarity, flow, and wording of an existing draft. |

## Reuse a skill

Take the complete skill directory, including `SKILL.md` and its bundled resources, and install it using your agent tool's skill installation method. For a reproducible setup, use the same Git commit or release tag across environments.

Once the skill is installed in Codex, invoke it by name. For example, `$research-paper-reading Explain this paper using the attached PDF and verify the method against the linked repository.`
