# AGENTS.md

本仓库维护个人积累的可复用 Skills，供不同 Agent 平台和版本使用。根目录 [README.md](README.md) 面向使用者，维护技能索引。本文管理仓库级约定，具体任务的执行规则放在对应技能的 `SKILL.md`。

## 选择和维护技能

开始前先看索引，再读目标技能的 `SKILL.md` 和与任务相关的参考资料。现有论文技能各有分工。

- [research-paper-reading](research-paper-reading/SKILL.md) 用于论文精读、原图解读和源码交叉核验。
- [research-paper-writing](research-paper-writing/SKILL.md) 用于起草章节、调整论证结构和核对主张与证据。
- [research-paper-polishing](research-paper-polishing/SKILL.md) 用于已有稿件的措辞、段落衔接和可读性改进。

相同任务优先维护已有技能。有独立的触发场景和可复用流程时再新增技能目录。新增、移动或重命名时，同一轮更新 README 索引、受影响的相对链接和调用示例。

## 跨平台打包与版本

- 以技能目录作为分发单位。每个技能放在仓库根目录下的独立目录中，目录名与 `SKILL.md` 的 `name` 一致。按 [Agent Skills 规范](https://agentskills.io/specification) 编写 YAML frontmatter，`description` 写清用途和触发场景。
- `SKILL.md` 自带完成核心任务所需的规则。按需将细节、可执行脚本和模板放入同目录的 `references/`、`scripts/` 和 `assets/`，从入口用相对路径指向它们。必需资源随目录一同分发，避免依赖个人机器路径、聊天历史或仓库外的本地文件。
- 平台专用配置单独存放，例如 Codex 的 `agents/openai.yaml`。如果提供该文件，保持显示文案和 `$skill-name` 调用示例与 `SKILL.md` 一致。通用流程按所需能力描述。依赖特定工具或版本时，注明要求、可用的替代方式及缺少依赖时可完成的范围。
- 保持技能名、调用入口和既有用法稳定。必须改变调用方式或行为时，在变更说明中写明影响和迁移方式。需要在不同环境重现同一版技能时，使用同一个 Git commit 或发布标签。

## 提交前检查

- 检查 `SKILL.md` 的 YAML、目录名与 `name`、README 条目、相对链接和平台调用示例。环境提供 `skills-ref` 时，可运行 `skills-ref validate ./<skill-name>` 检查技能格式。
- 修改执行流程或脚本时，用代表性输入检查实际行为。新增依赖时检查缺失依赖的分支。记录验证过的平台和版本，以及尚未验证的部分。
- 引用论文、图片或代码作为示例时，标明原始出处。改动论文精读技能时，保留 `SKILL.md` 中原图、Caption 和源码的核验要求，检查缺少原图或公开代码时的处理，并继续区分作者报告、静态代码检查和独立复现。
- 检查提交范围和空白错误，包括新增文件。生成结果、临时草稿和机器本地配置留在工作区。
