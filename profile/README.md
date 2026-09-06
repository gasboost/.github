# gasboost

gasboost は、Google Apps Script でアプリケーションを開発するための TypeScript ライブラリ群です。

Google Apps Script は、Google Sheets、Drive、Gmail、Calendar などの Google Workspace サービスへ簡単にアクセスできる一方で、実行環境や開発モデルには通常の TypeScript アプリケーションとは異なる制約があります。

gasboost はそれらの境界を扱う小さなライブラリを提供し、Google Apps Script を使ったアプリケーションを一般的な TypeScript アプリケーションに近い構成で開発できるようにします。

## パッケージ

### アプリケーション

[gasboost/app](https://github.com/gasboost/app)

Google Apps Script アプリケーションのバックエンド、フロントエンド、ビルドを支援します。

- `@gasboost/app` — GET / POST / RPC を型安全に定義するバックエンドランタイム
- `@gasboost/vite` — Google Apps Script 向けの Vite ビルド
- `@gasboost/client` — フロントエンドから Google Apps Script を利用するためのクライアント
- `@gasboost/react` — React アプリケーション向けの統合

### データベース

[gasboost/db](https://github.com/gasboost/db)

Google Apps Script でデータを扱うためのライブラリです。

- `@gasboost/sheetorm` — Zod を利用した Google Sheets 向けの型安全な ORM

### テスト

[gasboost/fake](https://github.com/gasboost/fake)

Google Apps Script の組み込み API に依存するコードを、Node.js 上で実行・テストするための実装を提供します。

## 方針

gasboost は Google Apps Script を置き換えることを目的としていません。

Google Apps Script を使った一般的なアプリケーション開発で扱いにくい境界を補うことに集中しています。

- グローバル関数によるエントリーポイント
- フロントエンドとバックエンド間の RPC
- ビルド設定
- Google Sheets へのデータアクセス
- GAS API に依存するコードのローカルテスト

`SpreadsheetApp`、`DriveApp`、`GmailApp`、`CalendarApp` などの Google Workspace API は、これまで通り直接利用できます。

gasboost は、それらを利用してアプリケーションを構築するための基盤を提供します。

## License

MIT
