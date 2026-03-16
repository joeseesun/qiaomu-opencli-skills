# opencli Command Reference

All commands support: `-f table|json|yaml|md|csv` and `-v` (verbose/debug).

---

## BBC

| Command | Args | Description |
|---------|------|-------------|
| `bbc news` | `--limit N` (default 20, max 50) | BBC新闻头条 (RSS, no login needed) |

---

## Bilibili (B站)

| Command | Args | Description |
|---------|------|-------------|
| `bilibili hot` | `--limit N` (default 20) | B站热门视频 |
| `bilibili ranking` | `--limit N` (default 20) | 视频排行榜 |
| `bilibili search` | `--keyword <str>` (required), `--type video\|user`, `--page N`, `--limit N` | 搜索视频或用户 |
| `bilibili feed` | `--limit N`, `--type all\|video\|article` | 关注的人的动态时间线 |
| `bilibili dynamic` | `--limit N` (default 15) | 用户动态 feed |
| `bilibili history` | `--limit N` (default 20) | 我的观看历史 |
| `bilibili favorite` | `--limit N`, `--page N` | 我的默认收藏夹 |
| `bilibili following` | `--uid <id>` (可选，默认当前用户), `--page N`, `--limit N` (max 50) | 关注列表 |
| `bilibili me` | — | 当前用户个人资料 |
| `bilibili user-videos` | `--uid <id>` (required), `--limit N`, `--order pubdate\|click\|stow`, `--page N` | 指定用户的投稿视频 |
| `bilibili subtitle` | `--bvid <bvid>` (required), `--lang <code>` (可选，如 zh-CN, en-US, ai-zh) | 获取视频字幕 |

---

## BOSS直聘

| Command | Args | Description |
|---------|------|-------------|
| `boss search` | `--query <str>` (required), `--city <城市>`, `--experience <经验>`, `--degree <学历>`, `--salary <薪资>`, `--industry <行业>`, `--page N`, `--limit N` (default 15) | 搜索职位 |

**经验选项**: 应届/1年以内/1-3年/3-5年/5-10年/10年以上
**学历选项**: 大专/本科/硕士/博士
**薪资选项**: 3K以下/3-5K/5-10K/10-15K/15-20K/20-30K/30-50K/50K以上

---

## 携程 (Ctrip)

| Command | Args | Description |
|---------|------|-------------|
| `ctrip search` | `--query <str>` (required), `--limit N` (default 15) | 搜索城市或景点 |

---

## HackerNews

| Command | Args | Description |
|---------|------|-------------|
| `hackernews top` | `--limit N` (default 20) | 热门故事 (无需登录) |

---

## Reddit

| Command | Args | Description |
|---------|------|-------------|
| `reddit frontpage` | `--limit N` (default 15) | Reddit首页 / r/all |
| `reddit hot` | `--subreddit <name>` (可选), `--limit N` | 热门帖子 |
| `reddit search` | `--query <str>` (required), `--limit N` | 搜索帖子 |
| `reddit subreddit` | `--name <subreddit>` (required), `--sort hot\|new\|top\|rising`, `--limit N` | 指定 subreddit |

---

## 路透社 (Reuters)

| Command | Args | Description |
|---------|------|-------------|
| `reuters search` | `--query <str>` (required), `--limit N` (default 10, max 40) | 搜索新闻 |

---

## 什么值得买 (smzdm)

| Command | Args | Description |
|---------|------|-------------|
| `smzdm search` | `--keyword <str>` (required), `--limit N` (default 20) | 搜索好价商品 |

---

## Twitter / X

| Command | Args | Description |
|---------|------|-------------|
| `twitter timeline` | `--limit N` (default 20) | 首页时间线 |
| `twitter trending` | `--limit N` (default 20) | 热门话题 |
| `twitter search` | `--query <str>` (required), `--limit N` (default 15) | 搜索推文 |
| `twitter bookmarks` | `--limit N` (default 20) | 书签列表 |
| `twitter notifications` | `--limit N` (default 20) | 通知 |
| `twitter profile` | `--username <handle>` (required), `--limit N` (default 15) | 指定用户的推文 |
| `twitter followers` | `--user <handle>` (可选，默认自己), `--limit N` (default 50) | 粉丝列表 |
| `twitter following` | `--user <handle>` (可选), `--limit N` (default 50) | 关注列表 |
| `twitter post` | `--text <str>` (required) | 发推 |
| `twitter reply` | `--url <tweet_url>` (required), `--text <str>` (required) | 回复推文 |
| `twitter like` | `--url <tweet_url>` (required) | 点赞推文 |
| `twitter delete` | `--url <tweet_url>` (required) | 删除推文 |

---

## V2EX

| Command | Args | Description |
|---------|------|-------------|
| `v2ex hot` | `--limit N` (default 20) | 热门话题 (无需登录) |
| `v2ex latest` | `--limit N` (default 20) | 最新话题 (无需登录) |
| `v2ex topic` | `--id <topic_id>` (required) | 主题详情和回复 |
| `v2ex me` | — | 个人资料（余额/未读提醒）|
| `v2ex daily` | — | 每日签到并领取铜币 |
| `v2ex notifications` | `--limit N` (default 20) | 提醒（回复等）|

---

## 微博 (Weibo)

| Command | Args | Description |
|---------|------|-------------|
| `weibo hot` | `--limit N` (default 30, max 50) | 微博热搜 |

---

## 小红书 (Xiaohongshu)

| Command | Args | Description |
|---------|------|-------------|
| `xiaohongshu feed` | `--limit N` (default 20) | 首页推荐 Feed |
| `xiaohongshu search` | `--keyword <str>` (required), `--limit N` (default 20) | 搜索笔记 |
| `xiaohongshu notifications` | `--type mentions\|likes\|connections`, `--limit N` | 通知 |
| `xiaohongshu user` | `--id <user_id>` (required), `--limit N` (default 15) | 指定用户的笔记 |

---

## 雪球 (Xueqiu)

| Command | Args | Description |
|---------|------|-------------|
| `xueqiu hot` | `--limit N` (default 20) | 热门动态 |
| `xueqiu hot-stock` | `--limit N` (default 20, max 50), `--type 10\|12` (10=人气榜, 12=关注榜) | 热门股票榜 |
| `xueqiu feed` | `--page N`, `--limit N` (default 20) | 关注用户的动态时间线 |
| `xueqiu search` | `--query <str>` (required), `--limit N` (default 10) | 搜索股票（代码或名称）|
| `xueqiu stock` | `--symbol <code>` (required, 如 SH600519, AAPL) | 股票实时行情 |
| `xueqiu watchlist` | `--category 1\|2\|3` (1=自选, 2=持仓, 3=关注), `--limit N` | 自选股列表 |

---

## Yahoo Finance

| Command | Args | Description |
|---------|------|-------------|
| `yahoo-finance quote` | `--symbol <ticker>` (required, 如 AAPL, MSFT, TSLA) | 股票行情 |

---

## YouTube

| Command | Args | Description |
|---------|------|-------------|
| `youtube search` | `--query <str>` (required), `--limit N` (default 20, max 50) | 搜索视频 |

---

## 知乎 (Zhihu)

| Command | Args | Description |
|---------|------|-------------|
| `zhihu hot` | `--limit N` (default 20) | 知乎热榜 |
| `zhihu search` | `--keyword <str>` (required), `--limit N` (default 10) | 搜索内容 |
| `zhihu question` | `--id <question_id>` (required), `--limit N` (default 5, 答案数) | 问题详情和回答 |
