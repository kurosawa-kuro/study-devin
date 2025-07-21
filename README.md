# study-devin

WSL Ubuntu前提
よく使う技術は

### 🗂️ 技術スタックまとめ

### 🗂️ 技術スタックまとめ

| レイヤ             | 技術                       | ひと言まとめ                             | 典型的な扱いどころ                |
|------------------|--------------------------|--------------------------------------|-----------------------------|
| **フロントエンド**    | Vue 3                     | 軽量・Composition APIで開発体験◎               | SPA／MPA                    |
|                  | Pinia                     | Vue標準の状態管理。軽量でTypeScript相性良        | グローバルステート・キャッシュ       |
|                  | Tailwind CSS              | ユーティリティファーストCSS。脱BEM・クラス設計      | UI実装スピードアップ               |
|                  | Axios                     | PromiseベースのHTTPクライアント                 | API呼び出し                     |
| **バックエンド**      | Express                   | Node製ミニマルFW。学習コスト低                  | API／SSR                    |
|                  | openapi-backend           | OpenAPI仕様⇆ハンドラ自動紐付け                   | スキーマ駆動実装                 |
|                  | Jest／Supertest           | 単体テスト・エンドポイントテスト                | CIパイプライン                   |
| **データ**          | Prisma (ORM)              | 型安全・マイグレーション内蔵                    | DB操作・スキーマ管理              |
|                  | SQLite                    | 0コンフィグDB。開発・軽量本番向き                | ローカル／組み込み              |
| **ミドルウェア**      | dotenv                    | `.env` → `process.env`                      | 秘匿情報・環境切替               |
|                  | cors                      | CORSヘッダー自動付与                          | API公開・オリジン制御             |
|                  | Zod                       | 型安全バリデーションライブラリ                  | リクエスト／レスポンス検証         |
|                  | Morgan                    | HTTPリクエストログ出力                          | 開発・運用時の可視化               |
| **インフラ/運用**     | Ansible                   | 構成管理 (SSHプッシュ型)                        | VM構築・設定                   |
|                  | Terraform                 | IaC (クラウドAPIプル型)                        | AWS／GCPリソース定義            |

## 🤖 Devin 2.0 使い方

### 基本操作
- **起動**: Devin 2.0 を立ち上げ、プロジェクトディレクトリを指定
- **タスク指示**: 自然言語でやりたいことを伝える
- **進捗確認**: Devin が自動でファイル作成・編集・実行を行う過程を監視

### よく使うプロンプト例

#### 開発作業

---

# 🛠 開発タスク指示書

## 1. 概要

* **目的**: フロントエンド（Vue 3）とバックエンド（Express + OpenAPI + Prisma）を連携させたサンプルアプリを構築
* **成果物**:

  1. Vue 3 コンポーネント＋Tailwind CSS
  2. Express API エンドポイント + OpenAPI 仕様
  3. Prisma スキーマ追加＋マイグレーション
  4. 動作確認済みのフルスタック環境
  5. README（セットアップ & 起動手順）

## 2. 技術スタック

* **フロントエンド**

  * フレームワーク：Vue 3 (Options または Composition API)
  * 状態管理：Pinia
  * スタイリング：Tailwind CSS
* **バックエンド**

  * ランタイム：Node.js + Express
  * API 定義：OpenAPI (openapi-backend)
  * ORM：Prisma + SQLite
* **開発補助**

  * 環境変数管理：dotenv
  * CORS：cors
* **インフラ・運用**

  * IaC：Ansible / Terraform

## 3. データモデル

* **User**

  * `id` (PK)
  * `name` (string)
* **Micropost**

  * `id` (PK)
  * `title` (string)
* **リレーション**

  * User 1 : \* Micropost

## 4. 要件・制約

1. **言語**: JavaScript（TypeScript 不使用）
2. **認証**: ログイン機能は不要
3. **テスト**: テストコードは不要
4. **CRUD**: `update` と `destroy` アクションは不要
5. **デザイン**: 既存の `template-admin` (vue-express/src/template-admin)をできるだけ流用
6. **動作検証**: `concurrency` 等で Vue と Express の同時起動・通信ができること

## 5. タスク一覧

### 5.1 フロントエンド

* [ ] Vue 3 コンポーネントを新規作成

  * 機能例：投稿一覧コンポーネント、投稿作成フォーム
* [ ] Tailwind CSS でスタイリング

### 5.2 バックエンド

* [ ] Express API の新規エンドポイントを追加

  * GET `/users`
  * GET `/microposts`
  * GET `/microposts/:id`
  * POST `/microposts`
* [ ] OpenAPI 仕様定義ファイルを更新

  * paths, schemas を追加
  * openapi-backend でハンドラにマッピング

### 5.3 データベース

* [ ] Prisma スキーマに `User` / `Micropost` モデルを追加
* [ ] `prisma migrate dev` を実行し、SQLite DB を更新

### 5.4 全体動作

* [ ] concurrency 等でフロントとバックを同時起動
* [ ] API 呼び出し → データの登録／取得 が動作することを確認

## 6. ドキュメント

* **README に以下を追記**

  1. 前提条件（Node.js, npm/yarn, SQLite）
  2. 環境変数の設定方法（dotenv）
  3. インストール手順
  4. 各サービス（フロント／バック）起動コマンド
  5. 動作確認手順

---



#### デバッグ・修正
```
エラーログを確認して、問題箇所を特定・修正してください
TypeScriptの型エラーを解決してください
レスポンシブデザインの問題を修正してください
```

#### テスト・検証
```
新機能のユニットテストを作成してください
APIエンドポイントの統合テストを書いてください
フロントエンドのE2Eテストをセットアップしてください
```

### プロジェクト固有の指示

#### フロントエンド開発
- Vue 3 + Composition API を使用
- Pinia でステート管理
- Tailwind CSS でスタイリング
- TypeScript で型安全性を確保

#### バックエンド開発
- Express + openapi-backend で API 開発
- Prisma で DB 操作
- Jest + Supertest でテスト作成

#### 環境設定
- WSL Ubuntu 環境での開発を前提
- dotenv で環境変数管理
- SQLite をローカル DB として使用

### 注意点
- 既存のコード規約・アーキテクチャに従う
- セキュリティベストプラクティスを遵守
- 変更前に必ずバックアップまたはgitコミット
- 大きな変更は段階的に実装
