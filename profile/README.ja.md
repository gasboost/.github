<div align="center">

<img src="https://github.com/user-attachments/assets/11e09588-b6d5-44c1-af06-ac573342e86b" width="320" alt="gasboost logo" />

# gasboost

[English](./README.md) | **日本語**

### Google Apps Scriptのための、モダンなTypeScriptエコシステム。

モダンなTypeScriptツール、構造化されたアプリケーションアーキテクチャ、認証、認可、データアクセス、テスト、リアルタイム同期を使って、Google Apps Script上に本番運用可能なアプリケーションを構築します。

**Google Workspaceを中心に。その周りをモダンに。**

[Repositories](https://github.com/orgs/gasboost/repositories)

</div>

---

## なぜ「Boost」なのか？

gasboostという名前には、3つの目標を込めています。

### Boost GAS

Google Apps Scriptをアドホックなスクリプティングだけにとどめず、構造化されたアプリケーション開発のための、より強い基盤へ押し上げます。

gasboostはApps Scriptを置き換えません。シンプルなデプロイ、マネージドな実行環境、Google Workspaceとの深い統合というApps Scriptの強みを活かします。

### Boost Development

TypeScript、テスト、明確なアプリケーション境界、構造化されたデータアクセス、認証、認可、モダンなツール群によって、Apps Scriptアプリケーションの開発体験とソフトウェア品質を高めます。

### Boost Business

Google Workspaceによる自動化を、保守可能な業務アプリケーションへ発展させやすくします。

目標はApps Scriptのコードを単に書きやすくすることではありません。その上に構築されたシステムを、成長させ、運用し、変化させやすくすることです。

## なぜgasboostなのか？

Google Apps Scriptは、Google Workspaceと深く統合されたアプリケーションを構築するための、最も手軽な方法の一つです。

Google Sheets、Drive、Gmail、CalendarなどのWorkspaceサービスをランタイムから直接利用できるため、Apps Scriptは社内ツール、業務アプリケーション、自動化、デジタルトランスフォーメーションに特に強みを持ちます。

しかし、アプリケーションはしばしば小さなスクリプトの範囲を超えて成長します。

規模が大きくなるにつれて、開発者には次のような機能が必要になります。

- 構造化されたアプリケーションAPI
- 型安全なクライアント通信
- 認証とセッション管理
- 行レベルの認可
- 構造化されたデータアクセス
- ローカルテスト
- モダンなフロントエンドツール
- リアルタイム同期

**gasboostはGoogle Apps Scriptを置き換えることなく、これらの不足している要素を補います。**

Apps Scriptは引き続きランタイムであり、Google Workspaceへの橋渡しです。

gasboostは、その周りにモダンなアプリケーション開発エコシステムを構築します。

## エコシステム

gasboostは、単独でも、完全なアプリケーションスタックとして組み合わせても使える、責務の明確なパッケージ群で構成されています。

### Application

構造化されたバックエンドアプリケーションを構築し、型安全なAPIを通じてフロントエンドと通信します。

- アプリケーションエンドポイント
- GET / POSTハンドリング
- 型安全なRPC
- クライアント統合
- React統合
- Viteベースの開発

### Data

Google Sheets上に構造化されたデータアクセスを構築します。

- 型安全なクエリ
- Google Sheets ORM
- フィルタリングとソート
- リレーションとJOIN
- トランザクション
- マイグレーション
- 制約
- レプリケーション

### Security

認証と認可を、アプリケーションの第一級の関心事として扱います。

- 認証
- セッション管理
- 複数の認証方式
- Row Level Security
- 共有可能な認可ポリシー

### Testing

Apps Scriptに依存するコードをローカルで開発・テストします。

- インメモリのApps Script実装
- Apps Script APIのNode.js実装
- ユニットテスト
- インテグレーションテスト
- Vitestと親和性の高いワークフロー

### Realtime

Google Apps Scriptは、リアルタイムデータ配信のために設計されたプラットフォームではありません。

リアルタイム同期が必要な場合、gasboostはGoogle SheetsとGoogle Workspaceをアプリケーションの中心に保ちながら、Firebase Realtime DatabaseでApps Scriptを補完できます。

ReplicationとRow Level Securityによって、アプリケーションの認可ルールを重複させることなくデータを同期できます。

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

それぞれの技術が、明確な責務を持ちます。

**Google Apps Script**  
アプリケーションランタイムであり、Google Workspaceアダプターです。

**Google Sheets**  
Workspaceとの直接統合が価値を持つアプリケーションにおける、主要なデータストアです。

**Firebase Realtime Database**  
Apps Scriptだけでは不足する場合の、リアルタイム同期レイヤーです。

**gasboost**  
これらを一貫したTypeScriptアーキテクチャでつなぐ、アプリケーション開発レイヤーです。

## Philosophy

### Google Workspaceを中心に置く

gasboostはApps ScriptをNode.jsに変えようとはしません。

Apps ScriptとGoogle Workspaceの直接的な統合は、その最大の強みの一つです。

gasboostはその利点を保ちながら、周囲のアプリケーションアーキテクチャを改善します。

### エミュレーションに頼らない移植性

移植性とは、Google Apps Scriptを別のランタイムであるかのように見せることではありません。

gasboostは、アプリケーションを無理にランタイム非依存にするためにApps Scriptをエミュレートしません。

Apps Scriptの大きな価値の一つは、ビジネスとの距離が非常に近いことです。すでにGoogle Workspaceを利用している組織であれば、別のアプリケーションプラットフォームやインフラストラクチャを最初から導入することなく、手元にあるツールから自動化を始められます。

一方で、業務自動化は静的なものではありません。ビジネスが成長している、業務プロセスの管理が難しくなっている、既存の運用構造を変える必要がある。そうした理由から自動化が導入されることは少なくありません。ビジネスが変化すれば、それを支えるシステムにも成長の余地が必要です。

gasboostは、移植性をその成長経路を守るためのものと考えます。Apps Scriptの手軽さとWorkspaceとの深い統合を活かして始めながら、アプリケーションとしての構造を保つことで、規模や必要な能力が変わったときには、個々の責務を別のインフラストラクチャへ移せるようにします。

最初の日から最終的なインフラストラクチャを予測することが目的ではありません。今日の手軽な選択を、明日のアーキテクチャ上の行き止まりにしないことが目的です。

そのためにgasboostは、アプリケーションロジックとインフラストラクチャ固有のコードの間に、明確な境界を設けることを重視します。

Apps ScriptとGoogle Workspace APIは、価値を提供する場所では引き続き第一級の存在です。その一方で、業務ロジックは移植性が本当に必要な場所で移植可能な状態を保てます。

**Apps Scriptが得意なことにはApps Scriptを使う。それ以外の部分は、将来の変化に対応できるようにしておく。**

### TypeScript first

アプリケーションの契約、データ構造、クエリ、認証、認可、クライアント通信は、実用上可能な限り型安全であるべきです。

### 小さなパッケージ、一つのエコシステム

各パッケージは明確な責務を持ちます。

アプリケーションは必要な部分だけを利用しながら、エコシステム全体で一貫したアーキテクチャの恩恵を受けられます。

### ローカル開発を当たり前に

Apps Scriptアプリケーションも、慣れ親しんだTypeScriptツールを使ってローカルで開発・テストできるべきです。

### 適切な責務に、適切なインフラストラクチャを

Apps Scriptが得意なことは、Apps Scriptに任せます。

外部インフラストラクチャは、Apps Script自体が持たない能力を明確に補える場合にのみ導入します。

## はじめに

gasboostは、アプリケーションを構築する前に内部のパッケージ構成を理解する必要がないように設計されています。

推奨されるエントリーポイントは、gasboostプロジェクトジェネレーターです。

```bash
pnpm create gasboost
```

どの内部パッケージをインストールするかを考える代わりに、認証、データストア、認可、リアルタイム同期、フロントエンドアーキテクチャといった、アプリケーション上の判断を中心に構成できるよう設計されています。

プロジェクトジェネレーターが利用可能になるまでは、各リポジトリのインストール手順とパッケージ固有のドキュメントを参照してください。

## 何を作れるのか？

gasboostは、小さな単独スクリプトよりも多くの構造を必要とするアプリケーションを対象としています。

たとえば次のようなものです。

- 社内業務アプリケーション
- CRM・営業管理システム
- 予約・スケジュール管理システム
- 承認ワークフロー
- Google Workspace自動化
- セキュアなマルチユーザーアプリケーション
- Google Sheetsをデータストアとするデータ駆動アプリケーション
- リアルタイムアプリケーション
- Google Workspaceと外部サービスを組み合わせたアプリケーション

## Vision

Google Apps Scriptはすでに、アイデアからGoogle Workspaceと深く統合されたアプリケーションへ至るための、最短経路の一つを提供しています。

私たちの目標は、その周囲の開発体験も同じくらい強力にすることです。

> **モダンなGoogle Apps Script開発を、本格的なアプリケーション構築のための第一級の選択肢にする。**

## Community

gasboostはオープンソースです。

Issue、Discussion、ドキュメント改善、サンプル、インテグレーション、コードコントリビューションを歓迎します。

gasboostで何かを作ったら、ぜひ教えてください。

---

<div align="center">

**Google Apps Scriptで、モダンなアプリケーションを。**

MIT License

</div>
