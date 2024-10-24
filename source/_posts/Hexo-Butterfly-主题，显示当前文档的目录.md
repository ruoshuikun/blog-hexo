---
title: Hexo Butterfly 主题，显示当前文档的目录
date: 2024-10-24 18:44:51
tags:
---


在 Hexo Butterfly 主题中，显示当前文档的目录（TOC, Table of Contents）是一项常用功能。Butterfly 主题内置了该功能，只需进行简单的配置即可在文章页面显示目录。

### 步骤 1: 启用 TOC（目录）功能

1. **编辑主题配置文件**:
   打开 `themes/butterfly/_config.yml` 文件，找到与 TOC 相关的配置并启用：

   ```yaml
   toc:
     enable: true         # 启用文章目录
     number: true         # 是否显示目录的编号
     min_depth: 1         # 显示目录的最小标题级别
     max_depth: 6         # 显示目录的最大标题级别
   ```

   配置参数解释：
   - `enable`: 设置为 `true` 表示启用 TOC 目录功能。
   - `number`: 设置为 `true` 表示在目录项前显示编号。
   - `min_depth` 和 `max_depth`: 控制目录显示的标题级别，通常标题（h1 到 h6）用于生成目录，你可以根据需要调整范围。

2. **为文章启用目录**:
   在每篇文章的 Front Matter 中，可以通过以下方式启用或禁用目录：
   
   ```yaml
   ---
   title: "文章标题"
   toc: true   # 为该文章启用目录
   ---
   ```

   这样，目录会在文章内容的左侧或右侧显示，具体位置根据主题布局决定。

### 步骤 2: 控制目录显示位置

Butterfly 主题默认将目录放置在页面的右侧栏。如果你希望调整目录的显示位置，可以通过 `themes/butterfly/_config.yml` 文件中控制侧边栏的显示方式。

```yaml
aside:
  toc: true  # 右侧边栏显示目录
```

这样，目录会固定在页面的右侧，随着页面滚动。

### 步骤 3: 自定义目录样式

如果需要对目录的样式进行自定义，可以通过编辑主题的自定义样式文件：

1. 打开 `themes/butterfly/source/css/_custom.scss`，添加自定义样式。例如，你可以修改目录的边框、背景颜色、文字样式等：

   ```scss
   .toc {
     background-color: #f9f9f9;
     border: 1px solid #ddd;
     padding: 10px;
     font-size: 14px;
   }
   ```

2. 保存并重新生成站点：
   ```bash
   hexo clean && hexo g
   ```

### 小结

通过简单的配置，Hexo Butterfly 主题可以轻松实现文档目录（TOC）的显示。你可以在 `_config.yml` 文件中启用或禁用目录，并通过文章的 Front Matter 控制每篇文章是否显示目录。