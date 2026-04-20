# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Git 運用ルール

コードを変更するたびに、以下の手順で GitHub にプッシュすること：

1. 変更内容を確認する: `git diff`
2. 変更をステージング: `git add <files>`
3. コミット: `git commit -m "<変更内容を簡潔に説明するメッセージ>"`
4. プッシュ: `git push origin <branch>`

- コミットメッセージは変更の「なぜ」を中心に書く
- プッシュは毎回の変更ごとに行い、ローカルにコミットを溜め込まない
- `git push --force` は原則禁止（ユーザーが明示的に指示した場合のみ実行）

## デプロイ

- リポジトリ: https://github.com/aki2228824/task-board
- 公開 URL: https://aki2228824.github.io/task-board/
- `main` ブランチへの push で GitHub Actions が自動ビルド・デプロイ（`.github/workflows/deploy.yml`）
- Vite の `base` は `/task-board/` に固定（`vite.config.js`）

## 技術スタック

| 用途 | ライブラリ／ツール |
|------|------------------|
| UI フレームワーク | React 19 |
| ビルドツール | Vite 8 |
| スタイリング | CSS Modules なし・`App.css` に直書き（CSS 変数でライト／ダーク対応） |
| 状態管理 | `useState` / `useEffect`（外部ライブラリなし） |
| 永続化 | `localStorage`（キー: `task-board-tasks`） |
| Lint | ESLint 9（`eslint.config.js`） |

## コンポーネント命名規約

- ファイル名・コンポーネント名ともに **PascalCase**（例: `App.jsx`）
- 1 ファイル 1 コンポーネントを基本とする
- 対応する CSS ファイルはコンポーネントと同名（例: `App.jsx` → `App.css`）
- カスタムフックを切り出す場合は `use` プレフィックスの camelCase（例: `useTasks.js`）
