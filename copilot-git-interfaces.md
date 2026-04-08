# GitHub Copilot による Git / GitHub 操作 — インターフェイス別ガイド

> GitHub Copilot は複数のインターフェイスから Git・GitHub の操作を支援します。  
> 本ドキュメントでは、各インターフェイスでできることを一覧表にまとめたうえで、具体的な使用例を紹介します。

---

## 1. インターフェイス別 機能比較表

> **GitHub Web** 列には **Copilot Coding Agent**（クラウドエージェント）の機能も含みます。  
> Coding Agent 固有の機能には 🤖 マークを付記しています。

### 1-A. 3 インターフェイス共通の機能

以下の機能は **IDE・GitHub Web（Coding Agent 含む）・Copilot CLI** のすべてで利用可能です。

| 機能 | IDE | GitHub Web (Coding Agent 含む) | Copilot CLI | 補足 |
|---|:---:|:---:|:---:|---|
| **コードの自動補完・生成** | ✅ | ✅ | ✅ | |
| **コミットメッセージの自動生成** | ✅ | 🤖 | ✅ | Web は Coding Agent 経由 |
| **Git コマンドの提案・説明** | ✅ | ✅ | ✅ | |
| **Pull Request の作成** | ✅ | ✅ 🤖 | ✅ | |
| **Issue の操作（作成・コメント）** | ✅ | ✅ 🤖 | ✅ | |
| **ブランチの作成・管理** | ✅ | ✅ 🤖 | ✅ | |
| **ファイルの作成・編集・削除** | ✅ | ✅ 🤖 | ✅ | |
| **リポジトリの探索・質問応答** | ✅ | ✅ | ✅ | |
| **差分（diff）の説明** | ✅ | ✅ | ✅ | |
| **テストの生成・実行** | ✅ | 🤖 | ✅ | Web は Coding Agent 経由 |

### 1-B. 一部インターフェイス固有の機能

以下の機能は特定のインターフェイスでのみ利用できます。

| 機能 | IDE | GitHub Web (Coding Agent 含む) | Copilot CLI | 補足 |
|---|:---:|:---:|:---:|---|
| **Pull Request の要約生成** | — | ✅ 🤖 | — | GitHub Web / Coding Agent 固有 |
| **コードレビュー・提案** | ✅ | ✅ | — | IDE と GitHub Web のみ |
| **マージコンフリクトの解消支援** | ✅ | — | ✅ | IDE と CLI のみ |
| **ターミナルコマンドの実行** | ✅ | — | ✅ | IDE と CLI のみ |
| **Issue → 自動ブランチ → PR（全自動）** | — | 🤖 | — | Coding Agent 固有 |
| **インラインコード補完（タブ補完）** | ✅ | — | — | IDE 固有 |
| **会話の共有リンク生成** | — | ✅ | — | GitHub Web 固有 |

### 1-C. GitHub Mobile の対応状況

GitHub Mobile は上記 3 インターフェイスとは異なり、**質問応答に特化** したインターフェイスです。

| 機能 | GitHub Mobile |
|---|:---:|
| Git コマンドの提案・説明 | ✅ |
| リポジトリの探索・質問応答 | ✅ |
| 特定ファイル / コードへの質問 | ✅ |
| コード生成・Git 操作の直接実行 | — |

> **凡例:** ✅ = 対応 / 🤖 = Coding Agent 経由で対応 / — = 非対応または限定的

---

## 2. 各インターフェイスの概要

### 2.1 IDE（VS Code / JetBrains 等）

エディタ内の **Copilot Chat** および **インライン補完** を通じて、コーディングから Git 操作まで幅広く支援する。  
ローカルのワークスペースコンテキストを活用できるため、最も多機能なインターフェイス。

### 2.2 GitHub Web（github.com）

ブラウザ上の **Copilot Chat パネル** から利用。リポジトリ・Issue・Pull Request のコンテキストで質問できる。  
Pull Request の要約生成やコードレビュー支援など、GitHub プラットフォーム固有の機能が特徴。

### 2.3 Copilot CLI

ターミナル上で `copilot` コマンドを使い、自然言語で Git/シェルコマンドの提案を受けたり、コード変更を自律的に実行させたりできる。  
ファイルの編集・コマンド実行・Git 操作をターミナルから完結できる。

### 2.4 GitHub Mobile

スマートフォンアプリ上の **Copilot Chat** で、リポジトリやコードに関する質問ができる。  
外出先での確認・調査向き。Git 操作の直接実行はできないが、コマンドの提案や説明を得られる。

### 2.5 Copilot Coding Agent（クラウドエージェント）

GitHub Web 上で **Issue に Copilot を割り当てる** と、自律的にブランチ作成→コード変更→Pull Request 作成まで行う。  
人間がレビュー・マージするだけでよい、最も自動化度の高いインターフェイス。

---

## 3. インターフェイス別 具体的な使用例

### 3.1 IDE（VS Code / JetBrains 等）での使用例

#### 例 1：コミットメッセージの自動生成

ソースコントロールパネルでファイルをステージングした後、コミットメッセージ入力欄の ✨（スパークル）アイコンをクリックすると、変更内容に基づいたコミットメッセージが自動生成される。

#### 例 2：Git コマンドを Copilot Chat に質問

```
ユーザー: 直前のコミットメッセージを修正するにはどうすればいい？

Copilot: git commit --amend -m "新しいメッセージ" を使用します。
         すでに push 済みの場合は git push --force-with-lease が必要です。
```

#### 例 3：マージコンフリクトの解消

コンフリクトが発生したファイルを開くと、Copilot がインラインで解決案を提示する。Chat で「このコンフリクトを解決して」と指示することも可能。

#### 例 4：GitHub MCP ツールで Pull Request を作成

IDE の Copilot Chat（Agent モード）から、直接 GitHub API を呼び出して Issue の作成、Pull Request の作成・更新、ブランチ操作が可能。

```
ユーザー: この変更で "fix: correct typo in README" というタイトルの PR を作成して

Copilot: （GitHub MCP ツールを使用して PR を自動作成）
```

---

### 3.2 GitHub Web（github.com）での使用例

#### 例 1：Pull Request の要約を自動生成

Pull Request 作成時に「Copilot で要約を生成」ボタンをクリックすると、変更内容の概要が自動的に記述される。

#### 例 2：リポジトリの検索バーから質問

リポジトリの検索バーに自然言語で質問を入力し、「Ask Copilot」を選択する。

```
ユーザー: Where is authentication implemented in this codebase?

Copilot: 認証は src/auth/ ディレクトリに実装されています...（関連ファイルへのリンク付き）
```

#### 例 3：コードレビューでの提案

Pull Request のレビュー中に Copilot がコードの改善提案やバグの指摘をコメントとして自動投稿する。

#### 例 4：Issue の内容を Copilot に質問

Issue ページ上で Copilot Chat を開き、「この Issue を解決するにはどのファイルを修正すべき？」と質問できる。

---

### 3.3 Copilot CLI での使用例

#### 例 1：Git コマンドの提案

```bash
$ copilot "過去 1 週間のコミットをログで表示するコマンドは？"

# 提案されるコマンド:
git log --since="1 week ago" --oneline
```

#### 例 2：自律的なコード変更とコミット

```bash
$ copilot "README.md の typo を修正してコミットして"

# Copilot が自律的に：
# 1. README.md を読み込み
# 2. typo を検出・修正
# 3. git add && git commit を実行
```

#### 例 3：ブランチ操作の支援

```bash
$ copilot "feature/login ブランチを作成して切り替えて"

# 実行: git checkout -b feature/login
```

#### 例 4：シェルコマンドの説明

```bash
$ copilot "git rebase -i HEAD~3 は何をするコマンド？"

# Copilot: 直近 3 つのコミットを対話的にリベースするコマンドです。
# コミットの並べ替え、統合（squash）、メッセージ編集などが行えます。
```

---

### 3.4 GitHub Mobile での使用例

#### 例 1：リポジトリの概要を質問

```
ユーザー: What is the main purpose of this repo?

Copilot: このリポジトリは Git 操作の学習用マニュアルで、
         section1〜8 に分かれて基本操作を解説しています。
```

#### 例 2：特定ファイルのコードを質問

ファイルを開いた状態で Copilot アイコンをタップし、「Explain this file.」と質問すると、ファイルの概要を説明してくれる。

#### 例 3：外出先での Issue 確認

リポジトリの Issue ページから Copilot に「この Issue の原因として考えられるものは？」と質問し、調査の手がかりを得る。

---

### 3.5 Copilot Coding Agent での使用例

#### 例 1：Issue を Copilot に割り当てて自動修正

1. GitHub Web 上で Issue を開く
2. Assignees に **Copilot** を選択
3. Copilot が自動的にブランチを作成し、コードを修正し、Pull Request を作成
4. 人間がレビューしてマージ

#### 例 2：機能追加の Issue を渡す

```
Issue: 「ログイン画面にパスワードリセット機能を追加」

→ Copilot が自律的に：
  - feature ブランチを作成
  - 必要なコードを実装
  - テストを追加・実行
  - Pull Request を作成して結果を報告
```

---

## 4. まとめ：用途別おすすめインターフェイス

| やりたいこと | おすすめインターフェイス |
|---|---|
| コードを書きながら Git 操作もしたい | **IDE** |
| Pull Request のレビュー・要約を効率化したい | **GitHub Web** |
| ターミナルから素早くコマンドを調べたい | **Copilot CLI** |
| 外出先でリポジトリを確認・質問したい | **GitHub Mobile** |
| Issue を丸ごと自動で解決させたい | **Copilot Coding Agent** |
