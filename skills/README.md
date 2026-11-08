# 《隋唐行纪》项目技能

技能保存在本目录，由仓库根目录的 AGENTS.md 指引按需读取。

| 技能 | 在本项目中的用途 |
| --- | --- |
| [cocos-creator](cocos-creator/SKILL.md) | Cocos Creator 3.8 的 TypeScript 组件、场景、触控 UI、资源管理和 Android 构建 |
| [sui-tang-exploration](sui-tang-exploration/SKILL.md) | 隋唐地图、NPC 对话、任务、场景机关、知识图鉴与本地存档 |
| [cocos-character-sprites](cocos-character-sprites/SKILL.md) | 俯视角色行走帧的透明 PNG 拆分、落脚点检查和 Cocos 导入 |

Cocos 技能按需读取 3.8 和 Android 相关章节。API、命令及构建参数以实际工程版本和 [Cocos Creator 3.8 官方手册](https://docs.cocos.com/creator/3.8/manual/en/) 为准。探索技能由本项目维护。

## 官方开发工具

COCOS CLI 提供官方 MCP，用于操作已由 CLI 打开的工程。官方手册和 MCP 接入步骤集中在开发工具说明中。 [COCOS CLI MCP 接入](../docs/cocos-cli-mcp.md)

## 来源与许可

- Cocos 技能从固定提交导入，保留参考文件、模板、可选体检脚本与 MIT 许可证。 [cocos-creator-skill](https://github.com/hsiaozzz/cocos-creator-skill/tree/759ed2b5c3d3fd476096c89a6d8340e61ce012f8) · [MIT 许可证](cocos-creator/LICENSE)
- 角色精灵技能由本项目适配。两个 PNG 处理脚本原样取自仓库历史提交 `bf92e85` 所保存的 OpenAI Game Studio 版本，上游清单标注 MIT。 [上游流程](https://github.com/openai/plugins/blob/main/plugins/game-studio/skills/sprite-pipeline/SKILL.md) · [上游许可声明](https://github.com/openai/plugins/blob/main/plugins/game-studio/.codex-plugin/plugin.json)
