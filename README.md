# 独立写作站

这是一个零依赖的个人独立文章站，适合长期发布自己的内容。

## 本地启动

```bash
npm run build
npm run dev
```

然后打开 `http://localhost:4321`。

## 如何发布新文章

在 `content/posts/` 下新增一个 Markdown 文件，例如 `my-post.md`：

```md
---
title: 我的第一篇文章
description: 一句摘要
date: 2026-05-25
tags:
  - 随笔
  - 技术
---

这里写正文。
```

## 站点页面

- `/` 首页
- `/about/` 关于页
- `/tags/` 标签页
- `/posts/文章名/` 文章页
- `/studio/` 私人写作后台入口

## 优先部署到 Cloudflare Pages

推荐优先使用 Cloudflare Pages 托管这个项目。

### Cloudflare Pages 配置

- Repository: `Henry0620-tuzi/wenzhang`
- Production branch: `main`
- Framework preset: `None`
- Build command: `npm run build`
- Build output directory: `dist`
- Root directory: 留空

### Cloudflare Pages 环境变量

默认不需要设置环境变量。

重点：

- Cloudflare Pages 下不要设置 `SITE_BASE_PATH=/wenzhang/`
- Cloudflare Pages 应该直接使用根路径 `/`

也就是说，在 Cloudflare Pages 里：

```bash
npm run build
```

就够了。

## GitHub Pages 说明

这个项目也兼容 GitHub Pages，但需要子路径部署。

如果部署到 GitHub Pages：

```bash
SITE_BASE_PATH=/wenzhang/ npm run build
```

因为 GitHub Pages 对应的访问地址是：

`https://henry0620-tuzi.github.io/wenzhang/`

## 自定义域名

如果你用 Cloudflare Pages，再绑定自己的域名会更顺。

步骤一般是：

1. 在 Cloudflare Pages 项目里打开 `Custom domains`
2. 添加你的域名
3. 按提示完成 DNS 配置
4. 等待生效

## 推荐顺序

建议这样走：

1. 先在 Cloudflare Pages 跑通正式部署
2. 再接自己的域名
3. 最后继续完善作者信息、二维码和发布后台

## 下一步可升级

- 把 X 链接替换成你的真实主页
- 把二维码展示位替换成真实二维码图片
- 接入真正安全的后台登录
- 接入一键发布文章能力
