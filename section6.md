# 🔍 第6章  状態・差分の確認

> 作業ディレクトリの状態や変更内容の差分を確認します。

---

## 📋 手順

1. `git status` でファイルの変更状態を確認します。
2. `git diff` で具体的な変更内容を確認します。

---

## 💻 コマンドと実行結果

```bash
$ git status
```

```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
        modified:   index.html

Untracked files:
        style.css
```

```bash
$ git diff
```

```diff
diff --git a/index.html b/index.html
index 83db48f..f735c2d 100644
--- a/index.html
+++ b/index.html
@@ -1,4 +1,4 @@
-<title>My App</title>
+<title>My Awesome App</title>
```

```bash
# ステージ済みの差分
$ git diff --staged
```

> 💡 **Tip:** `git diff main..feature` でブランチ間の差分も確認できます。

---
[← 前章](section5.md) ｜ [目次へ戻る](gitmanual.md) ｜ [次章 →](section7.md)
