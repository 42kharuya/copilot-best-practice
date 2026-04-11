# Issue Drafts

このディレクトリは、このリポジトリを **「全部入りテンプレート」ではなく、「ブレない骨格 + 差し込み設計」** として育てるための Issue 下書き集です。

## 方針

Issue は次の3レイヤーで整理します。

1. **Core**
	- どのプロジェクトでも変わりにくい共通原則を完成版にする
2. **Slots / Blueprints**
	- プロジェクト固有情報の差し込み口を設計する
3. **Optional Packs**
	- 必要な人だけ使う具体例や拡張を別冊として提供する

### ドキュメント記述ルール

- 各ファイルの**文頭にそのファイル自体の使い方を書かない**
- 各機能や各ファイルの**詳細な使い方**は、`.github/about/` の集約ドキュメントにまとめる
- 各ファイル自身は、そのファイルが担う**本来の内容**に集中させる
- 初見向けの導線や全体像の説明は、README または `COPILOT_USAGE.md` 側で行う

## 優先順位

### Core
1. [AGENTS.md を「普遍原則」の完成版にする](01-complete-agents-md.md)
2. [copilot-instructions を「普遍原則」の完成版にする](02-complete-copilot-instructions.md)
3. [Core / Slots / Packs の構造に整理し直す](03-split-example-and-production-ready.md)

### Slots / Blueprints
4. [プロジェクト固有情報の差し込み設計を作る](04-add-stack-specific-templates.md)
5. [README を新戦略ベースで再構成する](05-rewrite-readme-for-adoption.md)
6. [導入シナリオではなく「導入判断ガイド」を作る](06-add-adoption-scenarios.md)
7. [比較表と判断フローを追加する](07-add-comparison-matrix.md)

### Optional Packs
8. [ケーススタディと拡張パックを別冊化する](08-add-case-studies.md)
9. [英語版ドキュメントを追加する](09-add-english-docs.md)
10. [更新ポリシーを明示する](10-define-maintenance-policy.md)

各ファイルはそのまま GitHub Issue に転記できるよう、以下の構成で揃えています。

- タイトル
- 背景
- 目的
- やること
- 完了条件
- 補足
