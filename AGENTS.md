# 《隋唐行纪》开发约定

## 产品与协作

- 项目中文名《隋唐行纪》，暂定英文名 Sui-Tang Chronicles；第一章《大运河：初入隋朝》。中文沟通与文档，代码标识使用英文。
- 游戏为手机浏览器优先的竖屏 H5、2D 俯视角、单人章节式历史探索 RPG。核心玩法是跑图、NPC 对话、任务、物品收集、机关解谜和历史知识收集。
- 历史范围为隋朝建立至安史之乱结束。史实须记录可核查来源；虚构人物、对白和情节须与史实区分，不能把生成内容当作历史证据。
- 第一版不主动增加战斗、多人同步、付费或排行榜。像素或国风卡通的具体美术方向在资源制作前确定，整章保持一致。

## 技术与数据边界

- 前端默认 Phaser + TypeScript + Vite；世界与角色在 Canvas 中渲染，中文对话、背包、任务日志等文字密集界面使用 DOM。
- 服务端优先 Node.js + TypeScript，负责账号、云存档和章节配置。数据库、后端框架和部署平台待实际开发需求明确后选择，当前没有可执行应用或测试命令。
- 游戏规则与状态独立于 Phaser 场景；场景负责渲染、动画、摄像机和输入适配。剧情、地图、任务和物品使用数据配置与稳定 ID。
- 游客无需登录即可试玩，本机保存进度；注册后可绑定进度，登录账号可跨设备恢复云存档。玩法主要在浏览器运行，不将云存档服务扩大成实时游戏服务器。
- 实现同步时覆盖断网、失败重试、重复请求和多设备存档冲突；不能静默覆盖进度。绑定已有云存档的账号时保留双方数据并明确选择或恢复流程。
- 服务端校验输入、认证和存档归属，防止跨账号读写；密钥仅放服务端环境配置，不提交真实凭据。

## 项目技能

本项目的技能保存在普通 `skills/` 目录，通过下列入口显式读取，不假设工具会自动发现。开始匹配任务前读取对应 `SKILL.md`，仅按需加载必要引用。项目约定和用户要求优先于技能中的通用模板；技能示例不能扩大产品范围。

| 任务 | 技能入口 |
| --- | --- |
| 游戏架构、状态与渲染分层 | [web-game-foundations](skills/openai/plugins/game-studio/skills/web-game-foundations/SKILL.md) |
| 地图、移动、碰撞、摄像机和场景 | [phaser-2d-game](skills/openai/plugins/game-studio/skills/phaser-2d-game/SKILL.md) |
| 竖屏布局、触屏、对话框、背包与 HUD | [game-ui-frontend](skills/openai/plugins/game-studio/skills/game-ui-frontend/SKILL.md) |
| 角色精灵、动画与资源归一化 | [sprite-pipeline](skills/openai/plugins/game-studio/skills/sprite-pipeline/SKILL.md) |
| 浏览器试玩、截图和视觉检查 | [game-playtest](skills/openai/plugins/game-studio/skills/game-playtest/SKILL.md) |
| 背包、任务和章节推进 | [rpg](skills/gamedev/skills/genres/rpg/SKILL.md) |
| NPC 分支对话、剧情条件与变量 | [dialogue-systems](skills/gamedev/skills/disciplines/dialogue-systems/SKILL.md) |
| 本地存档、云存档与恢复 | [save-systems](skills/gamedev/skills/disciplines/save-systems/SKILL.md) |
| 机关、谜题状态与通关条件 | [puzzle](skills/gamedev/skills/genres/puzzle/SKILL.md) |
| 地图路线、探索节奏和引导 | [level-design](skills/gamedev/skills/disciplines/level-design/SKILL.md) |
| 账号、REST 接口、数据库与服务端验证 | [nodejs-backend-patterns](skills/backend/plugins/javascript-typescript/skills/nodejs-backend-patterns/SKILL.md) |

技能版本、许可证、来源和更新步骤见 [skills/README.md](skills/README.md)。维护技能时保留上游署名，检查相对引用，不批量安装无关技能或修改全局技能目录。

## 验证与交付

- 按实际变更运行必要检查；命令必须来自已有项目配置。没有运行的检查明确说明，不编造通过结果。
- 玩法验证覆盖移动碰撞、场景切换、NPC 对话、接取与完成任务、收集物品、谜题完成和章节推进。
- 存档验证覆盖刷新恢复、游客绑定、登录恢复、断网重试、冲突处理和跨账号隔离。
- 浏览器验证覆盖手机竖屏、桌面试玩、触屏与键鼠、不同视口和安全区、中文字体及长文本；Canvas 视觉结果须配合截图或实际试玩检查。
- 为关键规则、存档和接口设计有意义的测试；不为低影响文档修改编写镜像测试。
- 当前配置阶段只验证指导文件与技能结构，不将这些检查描述为游戏测试。
