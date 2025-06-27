# GEMINI.md

## 1. プロジェクト概要

このプロジェクトは、個人の「人生設計」を総合的に支援するための多機能Webアプリケーションです。単なるメモ帳やToDoリストではなく、アイディアのひらめきからプロジェクトの創出、タスク管理、スケジュール管理、さらには家計簿やブログといった日々の活動まで、生活のあらゆる側面をシームレスに統合し、一元管理することを目的としています。

- **プロジェクト名:** IdeaDock
- **コンセプト:** 「ひらめき」を起点とした人生設計プラットフォーム
- **ターゲットユーザー:** 開発者自身

## 2. 主要機能（実装予定を含む）

既存の便利ツール（Notion, Trelloなど）の優れた点を参考にしつつ、それらを統合した「全部入り」のサービスを目指します。

- **アイディア管理:** クイックメモ、メモの構造化・昇格機能
- **タスク・プロジェクト管理:** ToDoリスト、リマインダー、カンバン、ガントチャート
- **スケジュール管理:** カレンダー機能
- **生活・資産管理:** 家計簿機能
- **情報発信・ポートフォリオ:** ブログ機能、ポートフォリオサイト生成
- **外部サービス連携:** GitHub等のアカウント連携
- **その他:** サーバー管理ダッシュボード、AIアシスタント、マルチプラットフォーム対応

## 3. 使用技術・ライブラリ

### フロントエンド
- **フレームワーク:** Next.js (v15)
- **言語:** TypeScript
- **UI:** React (v19), Tailwind CSS, Sass
- **テスト:** Jest, React Testing Library
- **リンター/フォーマッター:** ESLint, Prettier

### バックエンド
- **フレームワーク:** Django, Django REST Framework
- **言語:** Python
- **データベース:** SQLite3 (開発時), psycopg2 (PostgreSQL連携用)

### インフラ・その他
- **コンテナ技術:** Docker (docker-compose)

## 4. コーディング規約

- **フロントエンド:** Next.jsの推奨ESLintルール (`next/core-web-vitals`, `next/typescript`) に準拠します。コードフォーマットはPrettierを使用します。
- **バックエンド:** Djangoの標準的なコーディングスタイルに従います。

## 5. ビルド・開発・テストコマンド

**重要:** 依存関係はホストPCにはインストールされず、すべてDockerコンテナ内で管理されます。以下のコマンドは、原則として `docker exec` を介して各コンテナ内で実行してください。

### 開発環境
- **初期化:**
  - `docker compose up frontend-init --abort-on-container-exit`
  - `docker compose up backend-init --abort-on-container-exit`
- **ビルドと起動:**
  - `docker-compose build`
  - `docker-compose up -d`

### フロントエンド (コンテナ内)
- **開発サーバー:** `npm run dev`
- **ビルド:** `npm run build`
- **本番起動:** `npm run start`
- **Linter実行:** `npm run lint`
- **テスト実行:** `npm test` (※jestは導入済みですが、テストスクリプトの整備が必要です)

### バックエンド (コンテナ内)
- **開発サーバー:** `python manage.py runserver 0.0.0.0:8000`
- **マイグレーション実行:** `python manage.py migrate`
