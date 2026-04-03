# ↩️ 第8章  変更の取り消し

> 作業中・ステージ済み・コミット済みの各段階で変更を元に戻ます。

---

## 📋 取り消しの対象とコマンド

| 対象 | コマンド |
|---|---|
| 作業ディレクトリの変更 | `git restore <ファイル>` |
| ステージングの取り消し | `git restore --staged <ファイル>` |
| コミットの取り消し | `git reset --soft HEAD~1` |

---

## 💻 コマンドと実行結果

```bash
# 作業ディレクトリの変更を取り消し
$ git restore index.html
```

```
(出力なし / 元の内容に戻る)
```

```bash
# ステージングを取り消し
$ git restore --staged index.html
$ git status
```

```
On branch main
Changes not staged for commit:
        modified:   index.html
```

```bash
# 直前のコミットを取り消し（変更は保持）
$ git reset --soft HEAD~1
$ git log --oneline
```

```
a1b2c3d Add index.html
```

> ⚠️ **Note:** `git reset --hard` は変更も削除されるため扱いに注意が必要です。

---
[← 前章](section7.md) ｜ [目次へ戻る](gitmanual.md)
