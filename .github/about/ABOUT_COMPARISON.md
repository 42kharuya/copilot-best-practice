# GitHub Copilot 関連ファイルの比較と判断フロー

このドキュメントは、`AGENTS.md` / `instructions` / `agents` / `skills` / `workflows` の違いを、**どこに何を書くべきか**という観点で整理するための詳細ガイドです。

## 比較表

| 種類 | 適用範囲 | 常時適用 | 主な役割 | 主な編集者 | 推奨レイヤー | 保守頻度 | 導入優先度 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `AGENTS.md` | プロジェクト全体 | はい | 共通原則、変更姿勢、安全性 | リポジトリ管理者、チーム | **Core** | 低〜中 | 最優先 |
| `各ディレクトリ/AGENTS.md` | 特定ディレクトリ | はい | 局所文脈、構造、変更時の注意 | その領域の担当者 | **Blueprints / 差し込み** | 中 | 高 |
| `.github/copilot-instructions.md` | リポジトリ全体 | はい | 応答・提案の共通ルール | リポジトリ管理者、チーム | **Core** | 低〜中 | 最優先 |
| `.github/instructions/*.instructions.md` | 特定パス | はい | パス単位の実装ルール、レビュー観点 | その領域の担当者 | **Blueprints / 差し込み** | 中 | 高 |
| `.github/agents/` | 呼び出した時だけ | いいえ | 専門役割の付与 | 上級利用者、チーム | **Optional / 拡張** | 中〜高 | 中 |
| `.github/skills/` | 呼び出した時だけ | いいえ | 定型作業、実行手順の支援 | 上級利用者、チーム | **Optional / 拡張** | 中〜高 | 中 |
| `.github/workflows/` | 実行時 | いいえ | Cloud Agent の環境準備 | CI / 運用担当者 | **Optional / 拡張** | 高 | 必要時 |

## どこに何を書くか

### `AGENTS.md` に向いているもの

- どの変更でも共通で守ってほしい原則
- 安全性、確認優先ケース、検証姿勢
- 破壊的変更の扱い

### `各ディレクトリ/AGENTS.md` に向いているもの

- そのディレクトリの責務
- 関連ファイルや依存関係
- 変更影響が広がりやすい場所
- その場所で使う確認手順

### `.github/copilot-instructions.md` に向いているもの

- 応答トーン
- 結論の出し方
- 最小差分や推測回避などの普遍ルール

### `.github/instructions/*.instructions.md` に向いているもの

- パス単位のコーディング規約
- 設計やレビューの観点
- 技術スタック固有の実装方針

### `.github/agents/` に向いているもの

- レビュー役
- テスト生成役
- 調査役
- 特定タスク専用の役割定義

### `.github/skills/` に向いているもの

- lint 実行
- ログ解析
- 定型的な確認手順
- 一連の作業フロー

### `.github/workflows/` に向いているもの

- Cloud Agent が動くための依存関係セットアップ
- テストやビルドに必要な実行環境準備

## 判断フロー

次の順で判断すると整理しやすくなります。

1. **どの範囲に効く情報か？**
   - 全体なら `AGENTS.md` または `.github/copilot-instructions.md`
   - 特定ディレクトリや特定パスなら `各ディレクトリ/AGENTS.md` または `.github/instructions/*.instructions.md`
2. **常に効いてほしいか？**
   - 常に効いてほしいなら `AGENTS.md` / `instructions`
   - 呼び出したときだけでよいなら `agents` / `skills`
3. **役割は対話ルールか、実行支援か？**
   - 対話ルールなら `AGENTS.md` / `instructions`
   - 実行支援なら `skills` / `workflows`
4. **Cloud Agent の準備が必要か？**
   - 必要なら `workflows`
5. **本体に入れるべきか、差し込みにすべきか？**
   - どのプロジェクトでも共通なら Core
   - プロジェクト固有なら Blueprints 経由で差し込み
   - 強い前提を持つなら Optional Packs

## よくある迷い方

### 迷い方1: 技術スタックの説明を `AGENTS.md` に書く

これは原則として避けます。
技術スタック依存の内容は、`instructions` や局所 `AGENTS.md` に寄せます。

### 迷い方2: 一時的な作業ルールを Core に書く

一時的な内容は Core に向きません。
変化しやすい情報は、差し込み側または運用ドキュメント側で扱います。

### 迷い方3: `agents` と `skills` を同じものとして使う

- `agents` は**役割**
- `skills` は**作業手順**

役割を増やしたいのか、実行手順を増やしたいのかで分けて考えます。

## 関連リンク

- [README.md](../README.md)
- [導入判断ガイド](../../docs/adoption-decision-guide.md)
- [ルート AGENTS.md の説明](ABOUT_ROOT_AGENTS.md)
- [copilot-instructions.md の説明](ABOUT_COPILOT_INSTRUCTIONS.md)
- [カスタムエージェントの説明](ABOUT_AGENTS.md)
- [パス別 instructions の説明](ABOUT_INSTRUCTIONS.md)
- [skills の説明](ABOUT_SKILLS.md)
- [workflows の説明](ABOUT_WORKFLOWS.md)
