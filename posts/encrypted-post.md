---
title: 加密文章
published: 2024-01-15
description: 这是用于测试页面加密功能的文章
encrypted: true
pinned: true
password: "123456"
permalink: "encrypted-example"
tags: ["Test", "Encryption"]
category: "Technology"
---

此博客模板使用 [Astro](https://astro.build/) 构建。对于本指南中未提及的内容，您可以在 [Astro 文档](https://docs.astro.build/)中找到答案。

## 文章的 Front-matter

```yaml
---
title: 我的第一篇博客文章
published: 2023-09-09
description: 这是我的新 Astro 博客的第一篇文章。
image: ./cover.jpg
tags: [Foo, Bar]
category: 前端
draft: false
---
```

| 属性         | 描述                                                                                                                                                                                                   |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`       | 文章的标题。                                                                                                                                                                                      |
| `published`   | 文章的发布日期。                                                                                                                                                                            |
| `pinned`      | 此文章是否固定在文章列表顶部。                                                                                                                                                   |
| `description` | 文章的简短描述。显示在索引页上。                                                                                                                                                   |
| `image`       | 文章的封面图片路径。<br>1. 以 `http://` 或 `https://` 开头：使用网络图片<br>2. 以 `/` 开头：用于 `public` 目录中的图片<br>3. 不含任何前缀：相对于 Markdown 文件                                                                                                                                                                                                 |
| `tags`        | 文章的标签。                                                                                                                                                                                       |
| `category`    | 文章的分类。                                                                                                                                                                                   |
| `permalink`   | 文章的自定义永久链接。文章将可通过 `/posts/{permalink}/` 访问。示例：`my-special-article`（将可在 `/posts/my-special-article/` 访问）                                   |
| `licenseName` | 文章内容的许可证名称。                                                                                                                                                                      |
| `author`      | 文章的作者。                                                                                                                                                                                     |
| `sourceLink`  | 文章内容的来源链接或参考。                                                                                                                                                          |
| `draft`       | 如果这篇文章仍是草稿，则不会被显示。                                                                                                                                                    |

## 文章文件的放置位置

您的文章文件应放置在 `src/content/posts/` 目录中。您也可以创建子目录来更好地组织您的文章和资产。

```
src/content/posts/
├── post-1.md
└── post-2/
    ├── cover.png
    └── index.md
```

## 自定义永久链接

您可以通过在 Front-matter 中添加 `permalink` 字段来为任何文章设置自定义永久链接：

```yaml
---
title: 我的特别文章
published: 2024-01-15
permalink: "my-special-article"
tags: ["示例"]
category: "Technology"
---
```

设置自定义永久链接后：

  - 文章将可通过自定义 URL 访问（例如，`/posts/my-special-article/`）
  - 默认的 `/posts/{slug}/` URL 仍将有效
  - RSS/Atom 订阅源将使用自定义永久链接
  - 所有内部链接将自动使用自定义永久链接

**重要说明：**

  - 永久链接不应包含 `/posts/` 前缀（它将自动添加）
  - 避免在永久链接中使用特殊字符和空格
  - 最佳 SEO 实践是使用小写字母和连字符
  - 确保永久链接在所有文章中是唯一的
  - 不要包含开头或结尾的斜杠

## 工作原理

```mermaid
graph LR
    A[用户密码] --> B[bcrypt 哈希]
    B --> C[密码哈希]
    C --> D[提取前 32 个字符]
    D --> E[加密密钥]
    E --> F[AES 加密]
    F --> G[加密内容]
```
