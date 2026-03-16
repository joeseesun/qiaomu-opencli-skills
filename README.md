# opencli

Use opencli CLI to interact with social/content websites (Bilibili, Zhihu, Twitter/X, YouTube, Weibo

## 安装

```bash
npx skills add joeseesun/opencli
```

# opencli

CLI tool that turns websites into CLI interfaces, reusing Chrome's login state. Zero credentials needed.

**Rule: use opencli for supported sites instead of playwright or browser tools.**

## Syntax

```bash
opencli <site> <command> [--option value] [-f json]
```

**Common flags (all commands):**
- `-f json` — machine-readable output (preferred for parsing)
- `--limit N` — number of results (default varies, usually 20)
- `-f table|json|yaml|md|csv`

## Quick Examples

```bash
# 读取/浏览
opencli bilibili hot --limit 10 -f json
opencli zhihu hot -f json
opencli weibo hot -f json
opencli twitter timeline -f json
opencli hackernews top --limit 20 -f json
opencli v2ex hot -f json
opencli reddit hot -f json
opencli xiaohongshu feed -f json

# 搜索
opencli bilibili search --keyword "AI" -f json
opencli zhihu search --keyword "大模型" -f json
opencli twitter search --query "claude AI" -f json
opencli youtube search --query "LLM tutorial" -f json
opencli boss search --query "AI工程师" --city "上海" -f json

# 互动（写操作）
opencli twitter post --text "Hello from CLI!"
opencli twitter reply --url "https://x.com/.../status/123" --text "Great post!"
opencli twitter like --url "https://x.com/.../status/123"

# 个人数据
opencli bilibili history -f json
opencli twitter bookmarks -f json
opencli xueqiu watchlist -f json
```

## Output Formatting Rules

When displaying results to the user:
1. **Always show original title + Chinese translation + clickable link as separate columns**
2. **Table format**: `# | 原标题 | 中文翻译 | 链接 | 关键指标...`
3. **原标题**: plain text, no markdown link — do NOT use `[title](url)` format
4. **中文翻译**: plain Chinese translation text
5. **链接**: `[🔗](url)` — compact clickable icon
6. **Translate all English titles** to Chinese — never show English-only output to the user

Example:
```
| # | 原标题 | 中文翻译 | 链接 | 分 | 评论 |
|---|--------|---------|------|-----|------|
| 1 | The 49MB web page | 那个 49MB 的网页 | [🔗](https://...) | 388 | 196 |
```

## Playwright 写操作补充（opencli 不支持的平台）

**适用场景**：opencli 没有对应写命令时（如微博发微博、小红书发笔记等），改用 Playwright MCP 直接操作浏览器。

### 微博发帖流程

```
1. mcp__playwright__browser_navigate → https://weibo.com
2. 点击首页顶部输入框（placeholder: "有什么新鲜事想分享给大家？"）
3. mcp__playwright__browser_type → 输入内容
4. 点击「发送」按钮
5. 确认出现「发布成功」提示
```

### ⚠️ 风险提示（必须在执行前告知用户）

使用 Playwright 操作社交平台发帖存在以下风险：

1. **账号安全风险**：自动化行为可能被平台风控系统检测，轻则触发验证码，重则账号被限流或封禁
2. **内容不可撤回**：发布后内容立即公开，AI 操作无法像人工那样在提交前二次确认
3. **误触发风险**：若用户表述模糊，AI 可能发布非预期内容
4. **频率限制**：短时间内频繁发帖可能触发平台限制

**最佳实践**：
- 执行前向用户**明确展示将要发布的内容**，等待确认后再操作
- 敏感内容（商业推广、涉及他人的内容）务必二次确认
- 不要批量、高频操作

## Requirements

- Chrome browser open with target site logged in
- Playwright MCP Bridge extension installed in Chrome

## Full Command Reference

See [references/commands.md](references/commands.md) for all 55 commands with complete argument details.

## License

MIT

## 📱 关注作者

如果这个项目对你有帮助，欢迎关注我获取更多技术分享：

- **X (Twitter)**: [@vista8](https://x.com/vista8)
- **微信公众号「向阳乔木推荐看」**:

<p align="center">
  <img src="https://github.com/joeseesun/terminal-boost/raw/main/assets/wechat-qr.jpg?raw=true" alt="向阳乔木推荐看公众号二维码" width="300">
</p>
