# MicYou-Backend

部署在 Cloudflare Workers 上的 GitHub Release 通知机器人。

## 部署

```bash
npm install
npx wrangler login
npm run deploy
```

## 环境变量

```bash
npx wrangler secret put TG_BOT_TOKEN        # Telegram Bot Token
npx wrangler secret put TG_CHAT_ID          # 群组 ID
npx wrangler secret put GITHUB_WEBHOOK_SECRET  # Webhook 密钥
npx wrangler secret put GITHUB_TOKEN        # GitHub Token（可选）
npx wrangler secret put TG_THREAD_ID        # 话题 ID（可选）
npx wrangler secret put ADMIN_USER_IDS      # 管理员 ID（可选）
```

## 路由

| 路径 | 说明 |
|------|------|
| `/` | 管理页面 |
| `/telegram/webhook` | Telegram Webhook |
| `/github/webhook` | GitHub Webhook |
| `/changelog` | Changelog 页面 |
| `/changelog.md` | Changelog 原始文件 |
| `/sendAll` | 发送所有历史 Release |

## 常用命令

```bash
npm run dev      # 本地开发
npm run deploy   # 部署
npm run tail     # 查看日志
```