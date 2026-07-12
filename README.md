# 我的原则 · My Principles

每日晨读 · 知行合一 · 专注积星。部署于 GitHub Pages:https://jjj5666.github.io/principles/

## 结构

- `index.html` — 全部应用(单文件:今日仪表盘 / 原则清单 / 每日时间表 / 稳态检查)
- `manifest.webmanifest` + `sw.js` + `icons/` — PWA:可安装到手机主屏幕,离线可用
- 数据存 `localStorage`(键:`fc_d_YYYY-MM-DD`、`fc_streak`、`fc_last`),打开页面即自动与共享云端桶双向同步(`SYNC_URL`,npoint.io,格式 `{version:1, days, streak, last}`)。桶只是同步桥,本机永远保有全量数据;桶失效时改 `SYNC_URL` 换新桶即可

## 发布更新

改完 `index.html` 后,把 `sw.js` 里的 `VERSION` 号 +1(否则老访客可能长时间拿到缓存的旧版),然后:

```bash
git add -A && git commit -m "update" && git push
```

推送 main 分支后 GitHub Pages 自动发布,约 1 分钟生效。

## 手机安装(iPhone)

Safari 打开网址 → 分享 → 添加到主屏幕。之后从主屏幕图标进入,全屏无地址栏,像原生 App。
