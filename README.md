# slidev-sample

Qiita 連載「Slidev × GitHub Copilot」の検証用デッキ集です。
各回の記事で紹介するスライド変換例を実際に動かして確認するためのサンプルリポジトリです。

## 収録デッキ

| ファイル | 内容 |
|---|---|
| `slide02.md` | 第2回 — 基本設計書を Slidev で顧客説明資料へ変換する |

## セットアップ

```powershell
npm install
```

## 開発サーバー起動

```powershell
# 第2回デッキ
npm run dev
```

ブラウザで `http://localhost:3030` を開くとスライドが表示されます。

## PDF 出力

```powershell
npm run export
```

## 確認観点

1. 100% 表示で日本語の表見出しが読める
2. 125% 表示でも改行位置が不自然に崩れない
3. 表が潰れず、注記が本文と混在しない
4. 1 ページ 1 メッセージが維持されている

## リポジトリルートから実行する場合

```powershell
npm --prefix ".docs/slidev-sample" run dev
npm --prefix ".docs/slidev-sample" run export
```

## 運用ルール

VS Code 拡張と Copilot の運用ルールは [`ops-rules.md`](ops-rules.md) を参照してください。