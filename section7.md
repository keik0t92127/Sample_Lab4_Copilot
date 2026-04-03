# 📜 第7章  ログの確認

> コミット履歴を確認して変更の追跡や調査を行います。

---

## 📋 手順

1. `git log` でコミット履歴を表示します。
2. オプションを使って表示形式を絞り込みます。

---

## 💻 コマンドと実行結果

```bash
$ git log
```

```
commit e4f5a6b7c8d9e0f1a2b3c4d5e6f7a8b9c0d1e2f3
Author: Taro Yamada <taro@example.com>
Date:   Wed Apr 2 10:00:00 2026 +0900

    Update styles

commit a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0
Author: Taro Yamada <taro@example.com>
Date:   Tue Apr 1 09:00:00 2026 +0900

    Add index.html
```

```bash
# 1行で簡潔に表示
$ git log --oneline
```

```
e4f5a6b Update styles
a1b2c3d Add index.html
```

```bash
# ブランチのグラフ付き
$ git log --oneline --graph --all
```

```
* e4f5a6b (HEAD -> main) Update styles
* a1b2c3d Add index.html
```

> 💡 **Tip:** `git log --author="名前"` や `--since="1 week ago"` で絞り込み検索もできます。

---
[← 前章](section6.md) ｜ [目次へ戻る](gitmanual.md) ｜ [次章 →](section8.md)
