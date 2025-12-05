---
title: Markdown 扩展功能
published: 2024-05-01
updated: 2024-11-29
description: '阅读更多关于 Mizuki 中的 Markdown 功能'
image: ''
tags: [演示, 示例, Markdown, mizuki]
category: '示例'
draft: false 
---

## GitHub 仓库卡片
您可以添加动态卡片链接到 GitHub 仓库，在页面加载时，仓库信息会从 GitHub API 中拉取。

::github{repo="matsuzaka-yuki/Mizuki"}

使用代码 `::github{repo="matsuzaka-yuki/Mizuki"}` 创建一个 GitHub 仓库卡片。

```markdown
::github{repo="matsuzaka-yuki/Mizuki"}
```

## 提示框（Admonitions）

支持以下类型的提示框：`note` (注意) `tip` (提示) `important` (重要) `warning` (警告) `caution` (小心)

:::note
突出显示用户即使在略读时也应考虑的信息。
:::

:::tip
可选信息，帮助用户更成功。
:::

:::important
用户成功所必需的关键信息。
:::

:::warning
由于潜在风险，需要用户立即关注的关键内容。
:::

:::caution
某一行动可能带来的负面后果。
:::

### 基本语法

```markdown
:::note
突出显示用户即使在略读时也应考虑的信息。
:::

:::tip
可选信息，帮助用户更成功。
:::
```

### 自定义标题

提示框的标题可以自定义。

:::note[我的自定义标题]
这是一个带有自定义标题的注意。
:::

```markdown
:::note[MY CUSTOM TITLE]
这是一个带有自定义标题的注意。
:::
```

### GitHub 语法

> [\!TIP]
> [GitHub 语法](https://github.com/orgs/community/discussions/16925) 也受支持。

```
> [!NOTE]
> GitHub 语法也受支持。

> [!TIP]
> GitHub 语法也受支持。
```

### 剧透

您可以为您的文本添加剧透。文本也支持 **Markdown** 语法。

内容 :spoiler[被隐藏了 **ayyy**]！

```markdown
The content :spoiler[is hidden **ayyy**]!
```
