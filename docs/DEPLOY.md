# lumina サイト ｜ Vercel デプロイ手順

この `lumina-site/` フォルダがそのまま公開用の一式です。

```
lumina-site/
├─ index.html     ← サイト本体（これだけで動く静的サイト）
├─ vercel.json    ← 任意。キャッシュ/セキュリティヘッダ設定
└─ DEPLOY.md      ← この手順書
```

サーバ不要・ビルド不要の静的サイトなので、`index.html` を Vercel に置くだけで公開できます。

---

## 方法A：CLI で上げる（フォルダを直接デプロイ・最短）

ターミナルで：

```bash
# 1. Vercel CLI を入れる（初回だけ）
npm i -g vercel

# 2. このフォルダに移動
cd lumina-site

# 3. デプロイ（初回はログインとプロジェクト作成を聞かれる）
vercel

# 4. 本番URLとして確定する
vercel --prod
```

- 初回の `vercel` 実行時に、ブラウザでのログインと「新規プロジェクトを作るか」を聞かれます → そこで **lumina 専用プロジェクト**を作成。
- 出力される `https://<プロジェクト名>.vercel.app` が公開URLです。

---

## 方法B：GitHub 連携（更新を自動反映したい場合）

1. このフォルダを GitHub リポジトリに push。
2. [vercel.com](https://vercel.com) → **Add New… → Project** → そのリポジトリを Import。
3. Framework は **Other**（静的サイト）でそのまま Deploy。
4. 以降は GitHub に push するたびに自動で再デプロイされます。

---

## 独自ドメイン（任意）

Vercel のプロジェクト → **Settings → Domains** から、`lumina.◯◯◯` のような独自ドメインを割り当て可能。
取得済みドメインがあれば DNS を Vercel に向けるだけです。

---

## 現在の運用

GitHub `hasu-bot/lumina-site` の `main` に push すると Vercel に自動デプロイされます。
内容の正は `docs/lumina_design_spec.md`（v2）です。
