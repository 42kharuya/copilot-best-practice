<div align="center">
  <h1>🚀 日本最強の「GitHub Copilot 活用プロジェクトテンプレート」を作る</h1>
  <p><b>AIの進化スピードに、チーム全員でサバイブするための「集合知」リポジトリ</b></p>
</div>

このリポジトリは、GitHub Copilot を**高精度・低ブレで使うための共通OS**と、各プロジェクトの事情を**安全に差し込むための設計**をまとめたテンプレートです。

日々変わるAI活用ノウハウを、個人のメモではなく**再利用できる形**で蓄積し、日本語の現場でそのまま使いやすい形に整理することを目指しています。

## このリポジトリがやりたいこと

- どのプロジェクトでも使いやすい**普遍原則**を先に整える
- 技術スタックや構成差分は**差し込み設計**として分離する
- 具体例は本体から切り離し、**Optional Packs** として追加できるようにする

一言でいうと、

> **全部入りの完成品ではなく、ブレない骨格と安全な差し込み口を提供するリポジトリ**です。

## このテンプレートで完成版にするもの

- AIの基本動作原則
- 応答や提案のブレを減らすルール
- 変更時の安全性と検証姿勢
- どこに何を書くべきかの整理

## このテンプレートで差し込みにするもの

- 技術スタック
- ディレクトリ構造
- ビルド / テスト / 起動コマンド
- アーキテクチャや命名規約
- チーム固有の運用ルール

## リポジトリ戦略

### 3つのレイヤー

| レイヤー | 役割 | 代表例 |
| :--- | :--- | :--- |
| **Core** | どのプロジェクトでも変わりにくい共通原則 | `AGENTS.md`, `.github/copilot-instructions.md` |
| **Blueprints** | コピーして差し込む雛形 | `.github/blueprints/` |
| **Optional Packs** | 必要な人だけ追加する具体例や拡張 | `.github/optional-packs/` |

### なぜこの形にするのか

- 普遍部分を先に完成させると、初見でも導入しやすい
- 可変部分を Blueprint 化すると、汎用性を崩さず実用性を上げやすい
- 強い前提を持つ具体例を分離すると、本体の保守がしやすい

## はじめ方

1. まず [AGENTS.md](AGENTS.md) と [.github/copilot-instructions.md](.github/copilot-instructions.md) を Core として使う
2. プロジェクト固有情報は [.github/blueprints/project-context/README.md](.github/blueprints/project-context/README.md) と [.github/blueprints/project-context/project-context-checklist.md](.github/blueprints/project-context/project-context-checklist.md) から整理する
3. 必要な雛形を [.github/blueprints/README.md](.github/blueprints/README.md) から選び、実際の配置先へコピーして調整する
4. 強い前提を持つ具体例が必要なら [.github/optional-packs/README.md](.github/optional-packs/README.md) を使う

## 説明の読み分け

- [README.md](README.md)
  - このテンプレートリポジトリ自体の目的、戦略、参加方法
- [.github/COPILOT_USAGE.md](.github/COPILOT_USAGE.md)
  - Copilot 関連機能の全体像と使い分けの概要
- [.github/about/README.md](.github/about/README.md)
  - 各機能・各ファイルの詳細な使い方

README では、`.github` 配下の詳細仕様には踏み込みすぎず、**何を目指すリポジトリか**と**どう参加すれば価値が増えるか**に集中します。

## こんな人に向いています

- Copilot の出力ブレを減らしたい人
- チームで共通のAI運用ルールを持ちたい人
- 技術スタック依存のテンプレートではなく、骨格から整えたい人
- 具体例を追加しながらも、本体の汎用性を保ちたい人

## コントリビューションで歓迎するもの

- Core をより普遍的で壊れにくくする改善
- Blueprints の記入ガイドやチェックリストの改善
- Optional Packs として切り出せる具体例
- 日本語での導入判断をしやすくする説明改善
- 既存ドキュメントの責務分離を保つ改善

## コントリビューション時の考え方

- **本体に入れるべきか、Blueprint にすべきか、Optional Pack にすべきか**を先に判断する
- 特定技術だけで通用する内容は、できるだけ本体へ直接入れない
- 各機能の使い方説明は、本文の先頭ではなく [.github/about/README.md](.github/about/README.md) 側に寄せる
- 無関係な整理や全面リライトを混ぜず、目的ごとに小さく改善する

## 主要ディレクトリ

```text
.
├── AGENTS.md
├── README.md
└── .github/
    ├── copilot-instructions.md
    ├── COPILOT_USAGE.md
    ├── about/
    ├── blueprints/
    ├── optional-packs/
    ├── agents/
    ├── instructions/
    ├── skills/
    └── workflows/
```

詳細な使い分けは [README.md](README.md) ではなく、[.github/COPILOT_USAGE.md](.github/COPILOT_USAGE.md) と [.github/about/README.md](.github/about/README.md) に集約します。

## 参加方法

次のような改善は、そのまま Pull Request にしやすいです。

- 既存 Blueprint の説明をわかりやすくする
- 導入判断を助けるチェックリストを追加する
- Optional Pack として切り出せるサンプルを追加する
- ドキュメント責務の境界をより明確にする

## 📕 参考資料 (References)

### 🤖 AGENTS.md (AIコーディングエージェント向け README)
- [agentsmd/agents.md](https://github.com/agentsmd/agents.md)
  - （AIコーディングエージェントに向けた「エージェント版 README」として活用されるオープンな標準フォーマットとベストプラクティス）

### 🌟 リポジトリ全体カスタムインストラクション (.github/copilot-instructions.md)
- [Adding repository custom instructions for GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)
  - （リポジトリ全体に適用されるグローバルなカスタムインストラクションの作成と設定についての公式ガイドライン）

### 🤖 カスタムエージェント (.github/agents/*.agent.md)
- [About custom agents - GitHub Docs](https://docs.github.com/en/copilot/concepts/prompting/about-custom-agents)
  - （カスタムエージェントの概要、YAMLフロントマターの記述方法などの基本仕様）
- [agentsmd/agents.md](https://github.com/agentsmd/agents.md)
  - （エージェントの定義に用いられるMarkdownベースのファイルフォーマットの標準リポジトリ）

### 📝 パス別カスタムインストラクション (.github/instructions/*.instructions.md)
- [Adding repository custom instructions for GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)
  - （Globパターンを使った適用範囲の設定 `applyTo` や使用除外設定 `excludeAgent` などの構成方法の詳細）
- [About customizing GitHub Copilot responses - GitHub Docs](https://docs.github.com/en/copilot/concepts/prompting/response-customization)
  - （GitHub Copilotのレスポンスカスタマイズ全般に関する基本概念と優先順位の理解）

### 🧰 エージェントスキル (.github/skills/*/SKILL.md)
- [About agent skills - GitHub Docs](https://docs.github.com/en/copilot/concepts/agents/about-agent-skills)
  - （エージェントが専門タスクを実行する際に呼び出せる指示・スクリプト群 `SKILL.md` の概念と仕様・配置場所）
- [Creating agent skills for GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/cloud-agent/create-skills)
  - （ディレクトリ構造、YAMLフロントマター、などの実践的作成方法）

### ☁️ Copilot Cloud Agent ワークフロー (.github/workflows/copilot-setup-steps.yml)
- [Adding GitHub Copilot cloud agent to your organization - GitHub Docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/add-copilot-cloud-agent)
  - （GitHub Copilot Cloud Agentの導入方法全般について）
- [Configuring runners for GitHub Copilot cloud agent in your organization - GitHub Docs](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-for-organization/configure-runner-for-coding-agent)
  - （`copilot-setup-steps.yml` を用いた依存関係の自動インストール、専用ジョブの構成ルール、使用可能な属性などの公式要件）
