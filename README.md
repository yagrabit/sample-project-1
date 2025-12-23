# Sample Project 1

pnpmとTurborepoを使ったヘッドレスCMSプロジェクト

## プロジェクト構成

```
sample-project-1/
├── apps/
│   └── cms/          # ヘッドレスCMS（Next.js + Hono）
├── packages/
│   ├── database/     # Drizzle ORM設定とスキーマ
│   ├── config/       # 共通設定（TypeScript、ESLintなど）
│   └── ui/           # 共通UIコンポーネント（今後追加予定）
├── pnpm-workspace.yaml
├── turbo.json
└── package.json
```

## 技術スタック

- **Next.js** - フルスタックフレームワーク
- **Hono** - 軽量APIフレームワーク
- **pnpm + Turborepo** - モノレポ管理
- **Turso (SQLite)** - データベース
- **Drizzle ORM** - TypeScriptファーストのORM
- **Valibot** - バリデーション
- **Tailwind CSS** - スタイリング

## セットアップ

1. 依存関係のインストール:
```bash
pnpm install
```

2. 環境変数の設定:
```bash
cp .env.example .env
# .envファイルを編集してTursoの認証情報を設定
```

3. データベースのマイグレーション:
```bash
pnpm --filter @repo/database db:push
```

4. 開発サーバーの起動:
```bash
pnpm dev
```

## 開発コマンド

- `pnpm dev` - 開発サーバーを起動
- `pnpm build` - プロダクションビルド
- `pnpm lint` - リント実行
- `pnpm format` - コードフォーマット

## データベース管理

- `pnpm --filter @repo/database db:generate` - マイグレーションファイルを生成
- `pnpm --filter @repo/database db:push` - スキーマをデータベースに反映
- `pnpm --filter @repo/database db:studio` - Drizzle Studioを起動

## 今後の予定

- [ ] ポートフォリオサイト (apps/portfolio)
- [ ] ブログサイト (apps/blog)
- [ ] 共通UIコンポーネント (packages/ui)
- [ ] HonoによるAPI実装
