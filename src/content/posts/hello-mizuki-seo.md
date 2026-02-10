---
title: 用 Mizuki 写博客：从发布到 SEO 的完整指南
published: 2026-02-11
updated: 2026-02-11
description: 介绍如何用 Markdown 在 Mizuki 主题里写文章，并让每篇文章都拥有独立的 meta 与 JSON-LD，对搜索引擎和社交分享更友好。
tags: [Mizuki, 博客, SEO, Markdown]
category: 指南
draft: false
pinned: false
comment: true
---

## 为什么选 Markdown

用 **Markdown** 写文章，可以专注内容本身：标题、段落、列表、代码块都用简单语法完成，无需关心排版。Mizuki 基于 Astro 构建，会把每篇 `.md` 编译成独立页面，并自动带上**专属的 meta 标签**和 **JSON-LD 结构化数据**，方便搜索引擎和社交平台抓取。

## 文章放在哪里

所有文章都放在 `src/content/posts/` 下，支持子目录，例如：

- `src/content/posts/hello-mizuki-seo.md` → 访问路径为 `/posts/hello-mizuki-seo/`
- `src/content/posts/生活/周末随笔.md` → 路径为 `/posts/生活/周末随笔/`

## 前言里建议写什么

每篇文章开头用 `---` 包住 YAML 前言，至少写上：

| 字段 | 作用 |
|------|------|
| **title** | 页面标题、分享标题、JSON-LD 标题 |
| **published** | 发布日期，用于排序和结构化数据 |
| **description** | 摘要，用于 meta description 和分享预览 |

如果希望分享时有图，再加上 **image**（封面图路径或 URL）。有 **updated** 时，会用于「最后修改时间」和 SEO 的 `article:modified_time`。

## 正文可以怎么写

正文就是标准 Markdown，例如：

- **加粗**、*斜体*、`代码`
- 列表、引用、表格
- 代码块（带语法高亮）
- 提示框：`> [!NOTE]`、`> [!TIP]` 等

> [!TIP]
> 写好 `description` 和 `image` 后，每篇文章的 og:image、twitter:image 和 JSON-LD 都会自动带上这些信息，无需再改模板。

## 小结

在 `src/content/posts/` 下新建 `.md`，填好 **title**、**published**、**description**（以及可选的 **image**、**updated**、**tags**、**category**），保存后构建或运行 `pnpm dev` 即可看到效果。每篇文章都会拥有独立的 meta 与 JSON-LD，对 SEO 和分享都很友好。
