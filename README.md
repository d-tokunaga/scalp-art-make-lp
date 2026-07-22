# 頭皮アートメイク ランディングページ

頭皮アートメイク・プロフェッショナルのブランドLP（静的サイト・モバイル最適化）。
`index.html` 1枚で完結します。外部ライブラリは不要（Google Fontsのみ読み込み）。

---

## 公開手順（GitHub → Vercel）

### 1. GitHubにリポジトリを作る
1. https://github.com にログイン（アカウントがなければ新規作成）
2. 右上「＋」→ **New repository**
3. Repository name を入力（例: `scalp-art-make-lp`）→ **Public** を選択 → **Create repository**

### 2. このフォルダをpushする
このフォルダはgit初期化・初回コミット済みです。ターミナルで以下を実行してください（URLはご自身のものに置き換え）:

```bash
cd scalp-art-make-lp
git remote add origin https://github.com/<あなたのユーザー名>/scalp-art-make-lp.git
git branch -M main
git push -u origin main
```

初回pushでユーザー名とパスワード（またはPersonal Access Token）を求められます。
※ GitHubは現在パスワード認証を廃止しているため、パスワード欄には
[Personal Access Token](https://github.com/settings/tokens) を発行して貼り付けます。

### 3. Vercelで公開する（無料）
1. https://vercel.com にアクセス → **Continue with GitHub** でログイン（無料のHobbyプランでOK。**購入は不要**）
2. **Add New… → Project**
3. さきほどのリポジトリを **Import**
4. Framework Preset は **Other**（自動判定でも可）、設定はデフォルトのまま
5. **Deploy** をクリック

数十秒で `https://scalp-art-make-lp.vercel.app` のようなURLが発行され、公開完了です。

以降は `git push` するたびにVercelが自動で再デプロイします。

---

## 独自ドメインを使いたい場合
Vercelのプロジェクト → **Settings → Domains** から独自ドメインを追加できます。
ドメイン自体はお名前.comやCloudflare等で取得が必要です（Vercel上でも購入可）。

## 写真の差し込み
`index.html` 内の症例カードは、Before/Afterがプレースホルダー表示です。
`<!-- 実写真を差し込む場合: <img src="..."> -->` のコメント位置に画像を入れると差し替わります。
画像は `images/` フォルダを作って置き、`src="images/case01-before.jpg"` のように参照します。
