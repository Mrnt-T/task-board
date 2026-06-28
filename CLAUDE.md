# CLAUDE.md

## プロジェクト概要

タスクボード（task-board）プロジェクト。

## デプロイ先

https://mrnt-t.github.io/task-board/

`main` ブランチへのプッシュで GitHub Actions が自動ビルド・デプロイする。

## 技術スタック

| 種別 | 技術 |
|------|------|
| フレームワーク | React 19 |
| ビルドツール | Vite 8 |
| 言語 | JavaScript (JSX) |
| スタイル | CSS (App.css / index.css) |
| データ永続化 | localStorage |
| CI/CD | GitHub Actions |
| ホスティング | GitHub Pages |

## コンポーネント命名規約

- ファイル名・コンポーネント名ともに **PascalCase** を使用する（例: `TaskItem.jsx`）
- `src/components/` 配下に機能単位で配置する
- コンポーネント単位の CSS は持たず、`App.css` でクラス名を一元管理する
- クラス名は **kebab-case** を使用する（例: `task-item`, `delete-btn`）

## Git 運用ルール

### コード変更のたびにプッシュする

コードを変更するたびに、必ず以下の手順でGitHubにプッシュすること：

1. 変更をステージングする
   ```bash
   git add <変更ファイル>
   ```

2. コミットメッセージを書いてコミットする
   ```bash
   git commit -m "変更内容を簡潔に説明するメッセージ"
   ```

3. GitHubにプッシュする
   ```bash
   git push origin <ブランチ名>
   ```

### コミットメッセージの規則

- 何を変更したかではなく、**なぜ変更したか**を書く
- 日本語でも英語でも可
- 例：`fix: ログイン時のバリデーションエラーを修正`、`feat: タスク一覧のフィルター機能を追加`

### ブランチ運用

- `main` ブランチへの直接プッシュは避ける
- 機能追加・バグ修正はフィーチャーブランチを切って作業する
- マージはプルリクエスト経由で行う

### プッシュ前チェック

- テストが通ることを確認してからプッシュする
- `main` への force push は禁止
