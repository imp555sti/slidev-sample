---
theme: default
title: 第2回サンプル - 基本設計書をSlidevへ変換する
info: |
  会員登録APIの基本設計書を顧客説明向け1ページへ要約した第2回用デッキ。
class: text-left
drawings:
  persist: false
mdc: true
---

# 第2回サンプル: 基本設計書をSlidevへ変換する

- 元原稿: `../examples/member-registration-basic-design.md`
- 目的: 基本設計書の一節を顧客説明向けに1ページへ要約する
- 確認観点: 日本語見出し、表、注記がWindows 11で崩れないか

---
layout: default
title: 元の基本設計書で伝えたいこと
---

# 元の基本設計書で伝えたいこと

**判断基準:** 顧客説明では「入力項目」「エラー時挙動」「登録完了条件」だけを判断できればよい

| 観点 | 設計書の要旨 |
|------|--------------|
| 入力項目 | メールアドレス、会社名、担当者名、電話番号 |
| エラー時挙動 | 重複時は 409、入力不備は 400 |
| 登録完了条件 | 確認メール送信まで完了していること |

> 桁数制約や保存形式は補足資料へ分離し、本文は説明判断に必要な情報だけを残す

---
layout: default
title: 会員登録APIの基本設計
---

# 会員登録APIの基本設計

**判断基準:** 顧客説明では、入力項目と完了条件だけを1ページで判断できる形に要約する

| 観点 | 内容 |
|------|------|
| 入力項目 | メールアドレス、会社名、担当者名、電話番号 |
| エラー時挙動 | 重複は 409、入力不備は 400 |
| 完了条件 | 登録成功後に確認メールを送信 |

> 詳細な桁数制約や保存形式は補足資料へ分離する

---
layout: default
title: 表示確認の観点
---

# 表示確認の観点

1. 日本語の表見出しが 100% 表示で読める
2. 125% 表示でも改行位置が不自然に崩れない
3. 表の列数を 2 列に抑え、PDF出力でも潰れない
4. 注記が本文と混ざらず、補足情報として読める

```css
table {
  font-size: 0.9em;
}
```

---
src: ./styles.md
---
*** Add File: g:\Qiita\Slidev\.docs\slidev-sample\slides03.md
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
- 確認観点: 情報密度、見せる順序、補足分離が一貫しているか

---
layout: default
title: engineer版のページ
---

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

---
layout: default
title: executive版のページ
---

# executive版: 会員登録APIの説明ポイント

**結論:** 入力項目、失敗時の扱い、登録完了条件を1ページで判断できるようにする

- 入力は4項目に限定
- 異常時の応答は重複と入力不備の2系統で整理
- 登録完了後は確認メール送信まで保証

> 技術詳細は補足資料へ分離し、本文は説明責任に必要な要点だけを残す

---
layout: default
title: テンプレートで固定したルール
---

# テンプレートで固定したルール

1. engineer版はコードを含めてよいが、executive版は含めない
2. 箇条書きは最大5項目
3. 1ページ1メッセージを崩さない
4. 詳細制約は補足資料へ分離する

---
src: ./styles.md
---
*** Add File: g:\Qiita\Slidev\.docs\slidev-sample\slides04.md
---
theme: default
title: 第4回サンプル - 正本更新からAIサマリーまで
info: |
  docs 変更から Slidev 反映、AI レビューサマリー生成までを示す第4回用デッキ。
class: text-left
drawings:
  persist: false
mdc: true
---

# 第4回サンプル: 正本更新からAIサマリーまで

- 元原稿: `../examples/member-registration-basic-design.md`
- 目的: 正本更新 → スライド反映 → サマリー生成の一方向フローを示す
- 確認観点: 設計書と説明資料の乖離が起きない構造になっているか

---
layout: default
title: docsの更新内容
---

# docsの更新内容

```md
## 5. 登録完了条件

1. 必須項目がすべて入力されている
2. メールアドレスが未登録である
3. 確認メール送信が成功する
4. 利用規約への同意が保存されている
```

> 正本の変更は `docs/` から始める

---
layout: default
title: Slidevへ反映したページ
---

# Slidevへ反映したページ

| 観点 | 内容 |
|------|------|
| 入力項目 | メールアドレス、会社名、担当者名、電話番号 |
| エラー時挙動 | 重複は 409、入力不備は 400 |
| 完了条件 | 確認メール送信と利用規約同意の保存 |

> 詳細設計は `docs/member-registration-basic-design.md` を参照

---
layout: default
title: AIレビューサマリーの例
---

# AIレビューサマリーの例

```text
- 登録完了条件に「利用規約への同意保存」を追加
- Slidev側の完了条件行も同内容へ更新済み
- 顧客説明での影響は「完了条件」の1行のみ
- 確認ポイント: 既存データ移行時に同意状態をどう扱うか
```

1. 正本の変更が説明資料へ追従している
2. 承認者はサマリーだけで変更の要点を把握できる
3. 二重文書作成が発生していない

---
src: ./styles.md
---
*** Add File: g:\Qiita\Slidev\.docs\slidev-sample\README.md
# Slidev Sample Decks

このディレクトリには、連載の各回に対応した検証用デッキを置いています。

- `slides02.md`: 第2回の基本設計書 → 説明資料の変換例
- `slides03.md`: 第3回の engineer / executive 書き分け例
- `slides04.md`: 第4回の docs 更新 → Slidev 反映 → AI サマリー例

実行例:

```powershell
npm run dev:02
npm run dev:03
npm run dev:04
```