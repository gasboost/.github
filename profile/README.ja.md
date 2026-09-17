<div align="center">

<img src="https://github.com/user-attachments/assets/11e09588-b6d5-44c1-af06-ac573342e86b" width="320" alt="gasboost logo" />

# gasboost

[English](./README.md) | **日本語**

### Google Apps Scriptのための、モダンなTypeScriptエコシステム。

TypeScriptによる開発、構造化されたアプリケーション設計、認証・認可、データアクセス、テスト、リアルタイム同期などを組み合わせ、Google Apps Script上で本番運用を前提としたアプリケーションを構築できる環境を提供します。

**Google Workspaceを中心に。その周りをモダンに。**

[Repositories](https://github.com/orgs/gasboost/repositories)

</div>

---

## なぜ「Boost」なのか？

gasboostという名前には、3つの目標を込めています。

### Boost GAS

Google Apps Scriptを、その場限りのスクリプトを書くための環境にとどめず、構造を持ったアプリケーションを開発できる基盤へ押し上げます。

gasboostはApps Scriptを置き換えません。手軽なデプロイ、インフラ管理を意識せず使える実行環境、Google Workspaceとの深い統合といったApps Script本来の強みを活かします。

### Boost Development

TypeScript、テスト、責務の分離、構造化されたデータアクセス、認証・認可、モダンな開発ツールを組み合わせ、Apps Scriptアプリケーションの開発体験とソフトウェア品質を高めます。

### Boost Business

Google Workspaceを使った業務自動化を、継続的に保守・発展できる業務アプリケーションへ育てやすくします。

目標は、Apps Scriptのコードを単に書きやすくすることではありません。その上に作られたシステムを、事業や業務の変化に合わせて成長させ、運用し、改善し続けられるようにすることです。

## なぜgasboostなのか？

Google Apps Scriptは、Google Workspaceと深く連携したアプリケーションを構築するための、最も手軽な方法の一つです。

Google Sheets、Drive、Gmail、CalendarなどのWorkspaceサービスを実行環境から直接利用できるため、Apps Scriptは社内ツール、業務アプリケーション、業務自動化、DXと非常に相性のよい基盤です。

一方で、業務の自動化は小さなスクリプトから始まり、そのまま重要な業務システムへ成長することがあります。

規模が大きくなるにつれて、次のような仕組みが必要になります。

- 構造化されたアプリケーションAPI
- 型安全なクライアント通信
- 認証とセッション管理
- 行単位の認可
- 構造化されたデータアクセス
- ローカルでのテスト
- モダンなフロントエンド開発環境
- リアルタイム同期

**gasboostはGoogle Apps Scriptを置き換えることなく、これらの不足を補います。**

Apps Scriptは引き続きアプリケーションの実行基盤であり、Google Workspaceと接続するための中心的な役割を担います。

gasboostは、その周囲にモダンなアプリケーション開発のための仕組みを整えます。

## エコシステム

gasboostは、責務ごとに分かれた複数のパッケージで構成されています。それぞれを単独で利用することも、組み合わせて一つのアプリケーション基盤として利用することもできます。

### Application

構造化されたバックエンドアプリケーションを構築し、型安全なAPIを通じてフロントエンドと連携します。

- アプリケーションのエンドポイント
- GET / POST の処理
- 型安全なRPC
- クライアント連携
- React連携
- Viteを使った開発

### Data

Google Sheetsを利用したデータアクセスを、型安全かつ構造的に扱います。

- 型安全なクエリ
- Google Sheets ORM
- フィルタリングとソート
- リレーションとJOIN
- トランザクション
- マイグレーション
- 制約
- レプリケーション

### Security

認証と認可を、アプリケーションの中核的な要件として扱います。

- 認証
- セッション管理
- 複数の認証方式
- Row Level Security
- 共通化できる認可ポリシー

### Testing

Apps Scriptに依存するコードも、ローカル環境で開発・テストできるようにします。

- Apps Script APIのインメモリ実装
- Node.js上で利用できるApps Script API実装
- ユニットテスト
- 結合テスト
- Vitestを使ったテスト環境

### Realtime

Google Apps Scriptは、リアルタイムなデータ配信を目的として設計された基盤ではありません。

リアルタイム同期が必要な場合は、Google SheetsとGoogle Workspaceをアプリケーションの中心に保ったまま、Firebase Realtime DatabaseでApps Scriptを補完できます。

ReplicationとRow Level Securityを組み合わせることで、アプリケーション側の認可ルールを重複して実装せずにデータを同期できます。

## アーキテクチャ

典型的なgasboostアプリケーションは、次のような構成になります。

```text
React
  │
  ▼
Type-safe Client
  │
  ▼
Application Runtime
  │
  ├── Authentication
  ├── Row Level Security
  ├── Business Logic
  │
  ├── Google Workspace
  │     ├── Gmail
  │     ├── Calendar
  │     ├── Drive
  │     └── Sheets
  │
  └── Data Layer
        ├── Query
        ├── Sheet ORM
        └── Replica
              │
              ▼
        Firebase Realtime Database
```

それぞれの技術に、明確な役割を持たせます。

**Google Apps Script**  
アプリケーションの実行基盤であり、Google Workspaceと接続するためのアダプターです。

**Google Sheets**  
Google Workspaceとの直接的な連携が価値を持つアプリケーションにおいて、主要なデータストアとして利用します。

**Firebase Realtime Database**  
Apps Scriptだけでは扱いにくいリアルタイム同期を担います。

**gasboost**  
これらを一貫したTypeScriptアーキテクチャでつなぐ、アプリケーション開発のためのレイヤーです。

## 設計思想

### Google Workspaceを中心に置く

gasboostは、Apps ScriptをNode.jsのような別の実行環境へ作り替えることを目指していません。

Apps ScriptからGoogle Workspaceの各サービスを直接利用できることは、Apps Scriptが持つ大きな強みです。

gasboostはその強みを残したまま、アプリケーションとして必要な構造をその周囲に加えます。

### エミュレーションに頼らない移植性

移植性とは、Google Apps Scriptを別の実行環境でもそのまま動くように見せかけることではありません。

gasboostは、どこでも同じコードを動かすためにApps Scriptを無理に再現することを目的としていません。

Apps Scriptの大きな価値の一つは、ビジネスとの距離が非常に近いことです。すでにGoogle Workspaceを利用している組織であれば、新しいアプリケーション基盤やインフラを最初から用意しなくても、今ある環境からすぐに業務の自動化を始められます。

一方、業務自動化が必要になる背景には、事業の成長、業務量の増加、管理方法の限界、既存の業務構造の見直しといった変化があります。ビジネスが成長するのであれば、それを支える自動化の仕組みも成長できなければなりません。

gasboostは、その成長余地を残すために移植性を重視します。最初はApps Scriptの手軽さとGoogle Workspaceとの近さを活かしながら、アプリケーションとしての構造を保つことで、将来、規模や要件が変わったときには必要な部分だけを別のインフラへ移せるようにします。

開発開始時点で、将来使うインフラをすべて決めておく必要はありません。重要なのは、今日の手軽な選択が、明日のアーキテクチャ上の行き止まりにならないことです。

そのためにgasboostは、業務ロジックとインフラ固有の処理の間に、明確な境界を設けることを重視します。

Apps ScriptとGoogle Workspace APIは、その強みが活きる場所では直接利用します。一方で、業務ロジックは特定のインフラに必要以上に依存させず、必要になったときに移せる構造を保ちます。

**Apps Scriptが得意なことにはApps Scriptを使う。それ以外の部分は、将来の変化に対応できるようにしておく。**

### TypeScriptを中心に

アプリケーションの契約、データ構造、クエリ、認証、認可、クライアント通信は、実用上可能な限り型安全であるべきです。

### 小さなパッケージ、一つのエコシステム

各パッケージは明確な責務を持ちます。

必要なパッケージだけを選んで利用しながら、エコシステム全体で一貫した設計の恩恵を受けられます。

### ローカル開発を当たり前に

Apps Scriptアプリケーションも、一般的なTypeScript開発と同じように、ローカル環境で開発・テストできるべきです。

### 適切な役割に、適切なインフラを

Apps Scriptが得意なことは、Apps Scriptに任せます。

外部インフラは、Apps Scriptだけでは実現しにくい機能を明確に補える場合にのみ導入します。

## はじめに

gasboostは、内部のパッケージ構成を理解してからでなければアプリケーションを作れない、という設計にはしていません。

推奨する入口は、gasboostのプロジェクトジェネレーターです。

```bash
pnpm create gasboost
```

どの内部パッケージを導入するかを先に考えるのではなく、認証方式、データストア、認可、リアルタイム同期、フロントエンド構成といったアプリケーション側の要件から構成を選べるように設計しています。

プロジェクトジェネレーターが利用可能になるまでは、各リポジトリのインストール手順とパッケージごとのドキュメントを参照してください。

## 何を作れるのか？

gasboostは、小さな単独スクリプトでは収まりきらない構造を必要とするアプリケーションを対象としています。

たとえば次のようなものです。

- 社内業務アプリケーション
- CRM・営業管理システム
- 予約・スケジュール管理システム
- 承認ワークフロー
- Google Workspaceを使った業務自動化
- 複数ユーザーで安全に利用するアプリケーション
- Google Sheetsをデータストアとして利用するデータ中心のアプリケーション
- リアルタイム同期を必要とするアプリケーション
- Google Workspaceと外部サービスを組み合わせたアプリケーション

## Vision

Google Apps Scriptはすでに、アイデアをGoogle Workspaceと深く連携したアプリケーションへ素早く形にするための、非常に短い経路を提供しています。

私たちの目標は、その周囲の開発体験も同じ水準まで引き上げることです。

> **モダンなGoogle Apps Script開発を、本格的なアプリケーションを構築するための有力な選択肢にする。**

## Community

gasboostはオープンソースです。

Issue、Discussion、ドキュメントの改善、サンプル、外部サービスとの連携、コードへの貢献を歓迎します。

gasboostで何かを作ったら、ぜひ教えてください。

---

<div align="center">

**Google Apps Scriptで、モダンなアプリケーションを。**

MIT License

</div>