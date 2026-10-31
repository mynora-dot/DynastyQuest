# 《隋唐行纪》项目技能

项目本地收录 11 个技能，按来源保留上游目录层级。入口由根目录 [AGENTS.md](../AGENTS.md) 显式指定，按需读取，不安装到全局目录。

## 技能索引

| 技能 | 用途 |
| --- | --- |
| [web-game-foundations](openai/plugins/game-studio/skills/web-game-foundations/SKILL.md) | 游戏架构与状态分层 |
| [phaser-2d-game](openai/plugins/game-studio/skills/phaser-2d-game/SKILL.md) | 地图、移动、碰撞与场景 |
| [game-ui-frontend](openai/plugins/game-studio/skills/game-ui-frontend/SKILL.md) | 竖屏界面、触屏和中文对话 |
| [sprite-pipeline](openai/plugins/game-studio/skills/sprite-pipeline/SKILL.md) | 精灵动画与资源规范 |
| [game-playtest](openai/plugins/game-studio/skills/game-playtest/SKILL.md) | 浏览器试玩与视觉检查 |
| [rpg](gamedev/skills/genres/rpg/SKILL.md) | 背包、任务与章节推进 |
| [puzzle](gamedev/skills/genres/puzzle/SKILL.md) | 机关解谜 |
| [dialogue-systems](gamedev/skills/disciplines/dialogue-systems/SKILL.md) | NPC 分支对话与剧情条件 |
| [save-systems](gamedev/skills/disciplines/save-systems/SKILL.md) | 本地与云端存档 |
| [level-design](gamedev/skills/disciplines/level-design/SKILL.md) | 地图路线与探索节奏 |
| [nodejs-backend-patterns](backend/plugins/javascript-typescript/skills/nodejs-backend-patterns/SKILL.md) | 账号、接口与数据库 |

## 固定来源与许可

- **openai**：[openai/plugins](https://github.com/openai/plugins/tree/0722921d5542fc593105c27bd52630babd8b8c2a)，提交 `0722921d5542fc593105c27bd52630babd8b8c2a`。
- **gamedev**：[gamedev-skills/awesome-gamedev-agent-skills](https://github.com/gamedev-skills/awesome-gamedev-agent-skills/tree/19d93f97c9c1ea0f8b306e77aa81e0d3e352d3e9)，提交 `19d93f97c9c1ea0f8b306e77aa81e0d3e352d3e9`。
- **backend**：[wshobson/agents](https://github.com/wshobson/agents/tree/7e2fb559cf4b824b27f1fec49fe88f7511066d26)，提交 `7e2fb559cf4b824b27f1fec49fe88f7511066d26`。

- OpenAI Game Studio 的 [原始插件清单](openai/plugins/game-studio/.codex-plugin/plugin.json) 声明作者为 OpenAI、许可为 MIT；该固定版本仓库根目录和 Game Studio 目录未提供独立许可证正文。本地保留原始清单及其图标资源，不自行补写或推断版权年份。
- 社区游戏技能库采用 Apache-2.0，保留 [LICENSE](gamedev/LICENSE) 与 [NOTICE](gamedev/NOTICE)。
- Node.js 后端技能保留上游 [MIT LICENSE](backend/LICENSE)。
- [sources.lock.json](sources.lock.json) 记录来源提交、收录路径、原始与本地文件 SHA-256 和本地调整，便于追溯与核验。

## 引用与使用边界

- 所选技能的完整目录（含 `agents/` 或 `references/`）均保留。Game Studio 另收录必要的 2D/通用参考文档、三个精灵处理脚本及原始插件元数据。
- 未安装专用 3D、其他引擎或多人技能。原文显式引用但不适用的 3D/路由入口改为固定提交的上游链接；具体变更见锁文件。技能原文仍有跨类型示例，仅采用本项目相关部分。
- 社区技能中的裸技能名是相关主题提示，不表示已安装。地图实现使用 Phaser 技能；不因示例提及 Godot、Unity、Roblox 或战斗而引入这些系统。
- 后端技能提到的 `javascript-testing-patterns` 是扩展阅读，本次未安装；实际验证遵循 AGENTS.md 与将来项目配置。
- `sprite-pipeline` 使用宿主已有的 `imagegen` 技能；三个附带脚本依赖 Python 3 与 Pillow。本次仅收录文件，不安装运行依赖或执行图片处理。脚本命令的工作目录见该技能正文。
- 浏览器试玩使用届时可用的浏览器工具或项目 Playwright 配置，本次未安装浏览器测试运行时。
- 存档技能的文件系统原子写入示例不能直接套到浏览器；实现时采用浏览器存储事务及服务端数据库事务等适合目标环境的机制。
- 项目约定优先于技能的通用建议。技能不能擅自增加战斗、商业化、实时联机或部署。

## 更新步骤

1. 在临时目录获取三个来源的新提交，固定完整提交 SHA，不以浮动分支作为最终记录。
2. 按索引逐一核对所选目录，更新完整目录及其必要参考、脚本和原始许可证/署名。
3. 保留来源层级，检查相对引用；不适用的专用技能仅保留固定提交的上游链接，不自动扩充安装范围。
4. 复核本地调整与宿主依赖，更新本文件、锁文件中的来源版本、文件哈希及变更记录。
5. 检查所有 SKILL.md 的名称/描述、11 个入口、相对链接、引用文档和脚本是否存在，再审查 Git 差异。不要将技能导入称为游戏功能测试通过。
