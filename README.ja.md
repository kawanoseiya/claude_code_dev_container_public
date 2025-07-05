#  Claude Code Dev Container

このリポジトリは、[Claude Code CLI](https://docs.anthropic.com/claude/docs/claude-code) を **VS Code の Dev Container 環境** に簡単にセットアップできるテンプレートです。

>  **Dev Container とは？**  
> Visual Studio Code (VS Code) の機能の一つで、特定のツールや設定が用意された開発用コンテナ環境を自動で構築・起動できます。  
> 通常のPC環境にソフトを個別インストールする必要がなく、すぐに開発が始められる便利な仕組みです。

---

##  セットアップ手順

### 1️. 事前準備

以下を事前にインストールしてください：

| ツール | 用途 | インストールリンク |
|-------|------|-------------------|
| [Visual Studio Code](https://code.visualstudio.com/) | ソースコード編集・Dev Container 対応エディタ | ✅ 必須 |
| [Dev Containers 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) | Dev Containerを扱うVS Code拡張 | ✅ 必須 |
| [Docker Desktop](https://www.docker.com/products/docker-desktop/) | Dev Container の実行に必要なコンテナ実行環境 | ✅ 必須（ローカル開発時） |

>  GitHub Codespaces を使う場合は Docker Desktop のインストールは不要です。

---

### 2️ Dev Container の起動

1. このリポジトリを VS Code で開きます。
2. コマンドパレット（`Cmd+Shift+P` または `Ctrl+Shift+P`）で `Reopen in Container` を実行。
3. 自動的に Claude Code CLI がセットアップされ、`claude` コマンドが使えるようになります。

---

### 3️. APIキーの設定

初回に `claude` コマンドを実行すると、APIキーの入力が求められます。指示に従って入力してください。

---

##  基本的な使い方

ターミナルを開いて以下を実行します：

```bash
claude
```

初回起動時は、以下のコマンドを使ってセットアップを行います（順番に実行してください）：

| コマンド | 内容 |
|---------|------|
| `/init` | CLAUDE.md を作成してプロジェクトの仕様を記述 |
| `/terminal-setup` | ターミナル補完などの初期設定 |
| `/install-github-app` | GitHub Actions連携のセットアップ（任意） |
| `/migrate-installer` | グローバルインストールからの移行処理（任意） |

> ⌨️ **ショートカット例**  
> - `Cmd+Esc`（Mac）または `Ctrl+Esc`（Windows）で Claude Code を起動  
> - `Ctrl+Alt+K` で @File 参照を挿入

---

##  Claudeの活用例：簡単なスクリプト作成

1. `claude` を起動
2. `/init` を実行して CLAUDE.md を作成
3. 以下のように依頼：
   ```
   create a bash script that backs up my project folder
   ```
4. Claudeの提案を確認・保存
5. 実際にスクリプトを実行して動作確認

---

##  Claudeでアプリ開発を進める例

1. `claude` を起動
2. `/init` を実行して CLAUDE.md に仕様を記述
3. Claudeに依頼：
   ```
   上記仕様書に基づいてFlutterプロジェクトを設計・実装して
   ```
4. Claudeの提案をレビュー・改善依頼
5. モジュール単位で分けて依頼し、テストコードも生成してもらう

---

##  ディレクトリ構成

| ファイル/ディレクトリ | 内容 |
|---------------------|------|
| `.devcontainer/devcontainer.json` | Claude CLIを含むDev Container構成。PATH設定済み。 |
| `.devcontainer/README.md` | このテンプレートの説明書。 |

---

## ⚠ 注意事項

- `claude` コマンドは Dev Container 起動時に自動で使えるようになります。
- **npx や npm 経由ではなく**、必ず Dev Container 内で `claude` を実行してください。
- Claude の提案は必ずレビューを行い、**安全で正確なコードのみを採用**してください。
- Claude Code VS Code 拡張を使用する場合、インストール後 `Cmd+Esc` で起動可能です。

---

## 🛠 トラブルシューティング

### Dev Container が起動しない場合

- Docker Desktop が起動していることを確認してください
- VS Code の Dev Containers 拡張がインストール・有効になっていることを確認してください
- 再起動後に `Reopen in Container` を再試行してください

---

##  参考リンク

- [Dev Container Features 公式仕様](https://containers.dev/implementors/features/)
- [Claude Code ドキュメント](https://docs.anthropic.com/claude/docs/claude-code)
- [Claude Code セキュリティガイド](https://docs.anthropic.com/claude/docs/claude-code-security)
- [Claude Code IDE 統合](https://docs.anthropic.com/claude/docs/claude-code-ide-integrations)

---

> ご意見・フィードバックは Issue や Pull Request にてお寄せください 
