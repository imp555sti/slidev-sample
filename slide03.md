---
theme: default
title: 第3回サンプル - テンプレートで品質をそろえる
info: |
  同じ基本設計書を engineer 向けと executive 向けに書き分ける第3回用デッキ。
class: text-left
drawings:
  persist: false
mdc: true
---

# 第3回サンプル: テンプレートで品質をそろえる

- 元原稿: `../examples/member-registration-basic-design.md`
- 目的: 同じ設計内容を読者別に書き分ける
- 確認観点: 情報密度、見せる順序、補足分離に加えて、タイトル帯・フッター帯・ページ番号が一貫しているか

<div class="template-spec-card">
  <div><strong>タイトル帯:</strong> 文書種別と章名を固定表示</div>
  <div><strong>フッター帯:</strong> 部門名、版番号、機密区分を固定表示</div>
  <div><strong>ページ番号:</strong> 右下固定でレビュー指摘をしやすくする</div>
</div>

---
layout: default
title: engineer版のページ
---

<div class="template-shell">
  <div class="title-band">
    <span>Partner Portal 基本設計テンプレート</span>
    <span>第3章 会員登録</span>
  </div>

# engineer版: 会員登録APIの設計判断

**判断基準:** 実装判断に必要な入力・エラー・完了条件を残す

| 観点 | 内容 |
|------|------|
| 入力項目 | メールアドレス、会社名、担当者名、電話番号 |
| エラー時挙動 | 重複は 409、入力不備は 400 |
| 完了条件 | 確認メール送信まで完了 |

```ts
const DUPLICATE_ERROR = 409
const VALIDATION_ERROR = 400
```

> 桁数制約や保存形式は補足資料に退避する

  <div class="footer-band">
    <span>Application Architecture Team</span>
    <span>Template v1.2 / Internal</span>
    <span class="page-no">- 1 -</span>
  </div>
</div>

---
layout: default
title: executive版のページ
---

<div class="template-shell executive-shell">
  <div class="title-band">
    <span>Partner Portal 基本設計テンプレート</span>
    <span>顧客説明向け要約</span>
  </div>

# executive版: 会員登録APIの説明ポイント

**結論:** 入力項目、失敗時の扱い、登録完了条件を1ページで判断できるようにする

- 入力は4項目に限定
- 異常時の応答は重複と入力不備の2系統で整理
- 登録完了後は確認メール送信まで保証

> 技術詳細は補足資料へ分離し、本文は説明責任に必要な要点だけを残す

  <div class="footer-band">
    <span>Application Architecture Team</span>
    <span>Customer Briefing Template</span>
    <span class="page-no">- 2 -</span>
  </div>
</div>

---
layout: default
title: テンプレートで固定したルール
---

<div class="template-shell rules-shell">
  <div class="title-band">
    <span>Partner Portal 基本設計テンプレート</span>
    <span>運用ルール</span>
  </div>

# テンプレートで固定したルール

1. engineer版はコードを含めてよいが、executive版は含めない
2. 箇条書きは最大5項目
3. 1ページ1メッセージを崩さない
4. 詳細制約は補足資料へ分離する

  <div class="footer-band">
    <span>Application Architecture Team</span>
    <span>Review Ready</span>
    <span class="page-no">- 3 -</span>
  </div>
</div>

---
src: ./styles.md
---
