# Karen's Dev Blog

使用 Hugo + PaperMod 主題建立的個人開發部落格。

## 工作流程

1. **`draft` 分支**：日常寫作與本地預覽（`hugo server -D`）
2. **合併到 `main`**：發布文章，自動觸發 Zeabur 部署
3. **線上驗證**：確認首頁、文章列表、圖片、標籤/分類導覽、程式碼高亮皆正常

## 本地開發

```bash
# 啟動本地預覽（含草稿）
hugo server -D

# 建立新文章（Page Bundle）
mkdir -p content/posts/my-new-post
touch content/posts/my-new-post/index.md
```

## 線上驗證清單

- [ ] 首頁可瀏覽
- [ ] 文章列表正常顯示
- [ ] 文章內圖片無 404
- [ ] 標籤 / 分類導覽可用
- [ ] 程式碼區塊有語法高亮
