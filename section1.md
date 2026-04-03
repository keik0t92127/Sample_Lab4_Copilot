# 📁 第1章  リポジトリの初期化

> ローカルに新しい Git リポジトリを作成し、バージョン管理を開始します。

---

## 🔄 フロー

```mermaid
flowchart LR
    A([任意のフォルダー]) -->|git init| B([.git フォルダー作成])
    B --> C([管理開始 ✅])
```

---

## 📋 手順

1. プロジェクトのディレクトリに移動します。
2. `git init` を実行してリポジトリを初期化します。
3. `.git` ディレクトリが作成されたことを確認します。

---

## 💻 コマンドと実行結果

```bash
$ cd my-project
$ git init
```

```
Initialized empty Git repository in C:/Users/user/my-project/.git/
```

```bash
# ディレクトリ名を指定して新規作成
$ git init new-repo
```

```
Initialized empty Git repository in C:/Users/user/new-repo/.git/
```

> ⚠️ **Note:** `.git` フォルダーを削除するとリポジトリ情報が失われます。誤って削除しないよう注意してください。

---
[← 目次へ戻る](gitmanual.md) ｜ [次章 →](section2.md)
