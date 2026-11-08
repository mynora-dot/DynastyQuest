# COCOS CLI 官方 MCP

官方 MCP 随 COCOS CLI 提供，由独立进程打开工程。PinK Beta 支持迁移 Creator 3.8.8 及以上工程。《隋唐行纪》以 Creator 3.8 为开发基线，评估官方 MCP 时使用 CLI 可打开的样例工程或迁移副本。 [COCOS CLI](https://github.com/cocos/cocos-cli) · [PinK Beta 兼容说明](https://www.cocos.com/post/9CHxd08s1FwVtj9KH0zRnG2kz5pTDBWz)

## 启动和连接

1. 按官方指南准备 COCOS CLI，运行 `cocos --help` 确认包含 `start-mcp-server`。 [安装指南](https://github.com/cocos/cocos-cli/blob/main/docs/en/quick-start.md)
2. 在 PowerShell 中将示例路径换成 CLI 可打开的工程目录，在前台启动服务。

   ```powershell
   cocos start-mcp-server --project 'D:/path/to/compatible-cocos-project' --port 9527
   ```

3. 在启动日志中确认地址为本机回环地址且路径为 `/mcp`。项目级配置已登记服务并默认禁用。服务就绪后，将 `url` 与实际地址对齐，设 `enabled = true` 并重启 Codex。Codex 从受信任的项目读取此配置。 [项目配置](../.codex/config.toml) · [COCOS CLI MCP 源码](https://github.com/cocos/cocos-cli/blob/4c7b89dd3188d800ac029522b245a2ead19db3e0/src/mcp/start-server.ts) · [OpenAI Docs 的 MCP 配置](https://learn.chatgpt.com/docs/extend/mcp)

   ```toml
   [mcp_servers.cocos_official]
   url = "http://127.0.0.1:9527/mcp"
   enabled = true
   ```

4. 在 Codex 的 `/mcp` 中确认已连接，先查询工程或场景信息以核对目标。使用完毕后在服务所在终端按 `Ctrl+C`。
