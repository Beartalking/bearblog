---
title: "我用两个 AI 搭了一个项目看板，自己几乎没动手"
datePublished: Wed Mar 04 2026 22:44:14 GMT+0000 (Coordinated Universal Time)
cuid: cmmcmj11l000302jl4vgp8yze
slug: ai-1
cover: https://res.cloudinary.com/dypkcf109/image/upload/v1772052954/obsidian/lmcmtl5swy83sfienuto.png
tags: productivity, design

---

# 我用两个 AI 搭了一个项目看板，自己几乎没动手

---

## 问题从哪里来

我本地 Claude Code 代码库里有 10 个项目在同时跑。Financial Adviser、Voice Daily Note、Content Publisher、Shorts Subtitle、CN Newsletter……每一个都有自己的目录、自己的 README、自己的当前状态，但它们之间没有任何联系。

我想知道"哪些项目在跑、哪些停了、下一步各自要做什么"的时候，只能在 Finder 里一个个点目录，或者凭记忆回忆。这不是什么大问题，但足够烦人，尤其是每周做计划复盘的时候。

我想要一个统一的视图。一个看板，三列：Active、Paused、Done，每张卡片上有描述、下一步、当前目标、已知问题、技术栈。

![](https://res.cloudinary.com/dypkcf109/image/upload/v1772052954/obsidian/lmcmtl5swy83sfienuto.png)

## 方案设计

用 Notion 做这个事情很自然，我已经把 Notion 当成工作中枢在用。

问题是怎么把 10 个项目的数据填进去。手动填是一个选项，但我更倾向于写脚本一次性导入，原因很简单：手动填 10 个项目、每个项目 8 个字段，很容易出错，而且枯燥。

我用 Claude Code 来规划方案。方案的核心决策有一个值得记录：要不要从各个项目的 README 自动解析数据？最终的答案是不要，直接硬编码在脚本里。原因是各个项目的 README 格式完全不统一，解析逻辑很脆弱，而且维护成本高。硬编码虽然"笨"，但稳定，一次性任务够用了。

![](https://res.cloudinary.com/dypkcf109/image/upload/v1772052985/obsidian/bvptgj0blu0hijay5fvq.png)


## Notion AI 出场

按常规做法，我需要在 Notion 里手动创建数据库，逐一添加 8 个 property，设置每个 property 的类型，再建 Board 视图。

但我换了个思路。我把 Claude Code 生成的数据库 schema（那张 property 表格）直接截图，打开 Notion AI，跟它说：按这个表格帮我创建一个数据库。

Notion AI 看了截图，把整个数据库结构建好了，包括所有字段和类型。我就点了一下"确认"，然后手动加了一个 Board 视图，整个过程不到30秒。

这是我没预料到的效率。

![](https://res.cloudinary.com/dypkcf109/image/upload/v1772053035/obsidian/qxcq2d8gajco6yv2qxud.png)


## Python 脚本

数据库建好之后，Claude Code 写了导入脚本。逻辑很直接：读取 `.env` 里的 `NOTION_TOKEN` 和 `DATABASE_ID`，遍历硬编码的 10 个项目字典，逐一调用 Notion API 创建页面。

数据内容需要我自己提供，这部分 Claude Code 帮我查阅了每个项目的 README 和现有文档，把各项目的描述、下一步、目标、已知问题整理成准确的文字，不是凭空编的。

Notion token 复用根目录 `.env` 里已有的，DATABASE_ID 从 Notion 的 URL 直接提取。

跑脚本：

```bash
python3 sync_to_notion.py
```

输出：

```
✓ Created: Financial Adviser [Active]
✓ Created: Voice Daily Note [Active]
✓ Created: Content Publisher [Active]
...
All 10 projects created successfully.
```

一行报错都没有。

## 两个 AI，各司其职

回头来看，整件事里有两个 AI 参与。

Claude Code 负责方案设计、数据整理和脚本编写，Notion AI 负责在 Notion 内部创建数据库结构。两者的边界很清楚，协作没有任何摩擦，因为它们各自在自己的主场工作。

我自己做了什么？跟 Notion AI 说了一句话，运行了一条命令，总计操作时间大概五分钟。

这不是说 AI 万能，脚本里的项目数据仍然需要人工判断和梳理，这件事 Claude Code 做了，但它调用的素材是我自己写的 README 和文档。垃圾进，垃圾出，这个规律没变。

![](https://res.cloudinary.com/dypkcf109/image/upload/v1772053083/obsidian/c0hjwdxgbuxn71syjcbo.png)


## 结果和边界

看板现在在 Notion 里运行，Board 视图三栏清晰，每张卡片内容完整。

这是一次性工具，脚本写完就封存了。之后在 Notion 里手动维护状态和进度，不需要再跑代码。

唯一要记住的一点：如果哪天需要重建数据库，直接再跑一次脚本就好，但要注意 Notion API 没有防重机制，会创建重复条目。加一个运行前检查的逻辑是可以的，但对这个用途来说没必要，知道这个限制，不重复跑就行。
