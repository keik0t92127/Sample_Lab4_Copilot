# 📌 第2章  ファイルのステージング

> 変更したファイルをコミット対象として「ステージングエリア」に登録します。

---

## 🔄 フロー

```mermaid
flowchart LR
    A([作業ディレクトリ]) -->|git add| B([ステージングエリア])
    B -->|git commit| C([リポジトリ])
```

---

## 📋 手順

1. `git status` で変更ファイルを確認します。
2. `git add` でステージングエリアに追加します。
3. 再度 `git status` でステージング状態を確認します。

---

## 💻 コマンドと実行結果

```bash
$ git status
```

```
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
```

```bash
$ git add index.html
$ git status
```

```
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
```

```bash
# すべての変更を一括追加
$ git add .
```

> 💡 **Tip:** `git add -p` を使うとファイルの一部分だけをステージングできます。

---
[← 前章](section1.md) ｜ [目次へ戻る](gitmanual.md) ｜ [次章 →](section3.md)
