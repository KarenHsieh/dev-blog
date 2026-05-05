---
title: "怎麼用 claude code 同時改兩個需求"
date: 2026-05-05
draft: false
tags: ["claude", "git", "worktree"]
categories: ["工具"]
summary: ""
---

Claude Code 有提供 worktree 這個功能可以同時跑多個獨立的 Claude 對話，每個 session 各自待在自己的工作目錄與分支上，這樣彼此檔案就可以隔開不互相汙染，跟 git worktree 的操作差不多。

```bash
claude -w [worktree 名稱]
```

執行這個指令以後，就會在 .claude/worktrees 目錄底下找到一個目錄，也就是這次對話的工作目錄。
但它會從目前 git 的 HEAD 切出一個新的分支，沒特別設定的話通常就是從 master / main 分支切出來的。

不過我現在遇到的情況是我開了一個 feature branch 在進行主要的 claude 對話修改，但同時又想要修正 sentry 回報的錯誤，所以我必須用 git worktree 的方式切一個有現在 branch 但又不互相影響的 code 環境給 claude 使用。

```bash
git worktree add [worktree 目錄路徑] -b [新 branch 名稱] [目前的 branch 名稱]
```

例如:

```bash
# 開新的 cli 執行
git worktree add ../sentry-fix -b sentry-fix feature/dataLayer-tracking

cd ../sentry-fix

claude
```
