---
title: "用 Hugo 打造個人部落格：從零開始的完整指南"
date: 2025-02-21
draft: false
tags: ["hugo", "blog", "static-site"]
categories: ["教學"]
summary: "這篇文章示範如何使用 Hugo 建立一個靜態部落格網站，包含基本設定、主題安裝與內容撰寫。"
---

## 為什麼選擇 Hugo？

Hugo 是目前最快的靜態網站產生器之一，使用 Go 語言開發，具備以下優勢：

- **極速建置**：數千篇文章也能在毫秒內完成
- **零依賴**：單一執行檔，不需要 Node.js 或 Ruby
- **豐富主題**：社群提供大量免費主題
- **Markdown 原生支援**：專注寫作，不必操心排版

## 快速開始

### 安裝 Hugo

在 macOS 上可以透過 Homebrew 安裝：

```bash
brew install hugo
hugo version
```

### 建立新站台

```bash
hugo new site my-blog
cd my-blog
```

### 安裝主題

以 [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 為例：

```bash
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

## 撰寫第一篇文章

Hugo 支援 **Page Bundle**，將文章與相關資源（圖片等）放在同一個資料夾中，方便管理：

```
content/posts/my-first-post/
├── index.md
└── cover.png
```

在 Markdown 中引用同資料夾的圖片非常簡單：

![範例圖片](sample-image.png)

## 程式碼高亮範例

Hugo 內建 Chroma 語法高亮引擎，支援多種語言。

### JavaScript

```javascript
function greet(name) {
  const message = `Hello, ${name}!`;
  console.log(message);
  return message;
}

greet('Hugo');
```

### CSS

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

## 本地預覽

啟動開發伺服器：

```bash
hugo server -D
```

開啟瀏覽器前往 `http://localhost:1313` 即可預覽。

## 小結

Hugo 讓建立部落格變得非常簡單，搭配 Git 工作流與 Zeabur 等平台，可以輕鬆實現自動部署。

> 更多資訊請參考 [Hugo 官方文件](https://gohugo.io/documentation/)。
