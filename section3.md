# 💾 第3章  コミット

![第3章 扉絵](images/chapter-3.svg)

> ステージングエリアの内容をスナップショットとしてリポジトリに永続保存します。

## 🌟 この章でわかること

- `git commit -m` で変更履歴を残す手順
- メッセージ付きコミットの基本的な考え方

---

## 🔄 フロー

```mermaid
flowchart LR
    A([ステージングエリア]) -->|git commit -m| B([コミット履歴に追加])
    B --> C([ハッシュ値で識別 🔑])
```

---

## 📋 手順

1. `git status` でステージング済みの変更を確認します。
2. メッセージを付けてコミットを実行します。
3. `git log` でコミットが記録されたことを確認します。

---

## 💻 コマンドと実行結果

```bash
$ git commit -m "Add index.html"
```

```
[main (root-commit) a1b2c3d] Add index.html
 1 file changed, 10 insertions(+)
 create mode 100644 index.html
```

```bash
# 追跡済みファイルならステージング省略可
$ git commit -am "Update styles"
```

```
[main e4f5a6b] Update styles
 1 file changed, 5 insertions(+), 2 deletions(-)
```

> ⚠️ **Note:** コミットメッセージは「何を・なぜ変更したか」が伝わる内容にしましょう。

---
[← 前章](section2.md) ｜ [目次へ戻る](gitmanual.md) ｜ [次章 →](section4.md)
