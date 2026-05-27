# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install      # install dependencies
npm run dev      # start dev server at http://localhost:5173
npm run build    # production build → dist/
npm run preview  # preview production build locally
```

## Architecture

- **`src/App.jsx`** — アプリ全体の唯一のコンポーネント。`tasks` state（配列）を `useState` で管理し、`useEffect` で変更のたびに `localStorage` へ保存する。初回マウント時は lazy initializer で `localStorage` から復元する。
- **`src/App.css`** — App.jsx 専用スタイル。グローバルスタイルは `src/index.css`。
- ビルドツール: **Vite** + **@vitejs/plugin-react**（Babel ベース）。設定は `vite.config.js`。

## 技術スタック

| レイヤー | 採用技術 |
|---|---|
| UI フレームワーク | React 19 |
| ビルドツール | Vite 6 |
| 状態管理 | useState（React 組み込み） |
| 永続化 | localStorage |
| スタイル | CSS（フレームワークなし） |
| 言語 | JavaScript（JSX） |

## コンポーネント命名規約

- コンポーネントファイルは **PascalCase**（例: `TaskItem.jsx`）
- コンポーネント関数も **PascalCase** でエクスポート（`export default function TaskItem`）
- CSS クラス名は **kebab-case**（例: `.task-list`, `.delete-btn`）
- イベントハンドラは `handle` プレフィックス（例: `handleKeyDown`）

## デプロイ先

**https://SHIOMA-1887.github.io/task-board/**

GitHub Pages へのデプロイは `npm run build` で `dist/` を生成し、`gh-pages` ブランチへ公開する。`vite.config.js` に `base: '/task-board/'` の設定が必要。

## 技術スタック

| レイヤー | 採用技術 |
|---|---|
| UI フレームワーク | React 19 |
| ビルドツール | Vite 6 |
| 状態管理 | useState（React 組み込み） |
| 永続化 | localStorage |
| スタイル | CSS（フレームワークなし） |
| 言語 | JavaScript（JSX） |

## コンポーネント命名規約

- コンポーネントファイルは **PascalCase**（例: `TaskItem.jsx`）
- コンポーネント関数も **PascalCase** でエクスポート（`export default function TaskItem`）
- CSS クラス名は **kebab-case**（例: `.task-list`, `.delete-btn`）
- イベントハンドラは `handle` プレフィックス（例: `handleKeyDown`）

## デプロイ先

**https://SHIOMA-1887.github.io/task-board/**

GitHub Pages へのデプロイは `npm run deploy` で行う。`dist/` が自動的に `gh-pages` ブランチへ公開される。

## Git Rules

- After every code change, commit and push to GitHub immediately.
- Never amend published commits; always create a new commit.
- Do not force-push to `main`.
