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

## 写真の差し込み（コード編集は不要）

症例カードは HTML を直接いじらず、**決まった名前で画像を `images/` フォルダに置くだけ**で自動表示されます。

### 命名規則
症例は上から順に `case01`, `case02`, … `case19` と番号が振られています（`index.html` の `CASES` 配列の並び順）。
各症例につき Before と After の2枚を、この名前で保存します:

```
images/case01-before.jpg
images/case01-after.jpg
images/case02-before.jpg
images/case02-after.jpg
   … （必要な分だけ）
```

- 拡張子は **.jpg を推奨**（.png でも自動で読み込みます）
- 写真を置いていない症例は、これまで通りプレースホルダー表示のまま
- 1件ずつ、用意できた分だけ順番に追加していけばOK

### どの症例が何番か
`index.html` を開き、`CASES` 配列の上から数えた順番が番号です（1件目＝case01）。
各症例の見出し（例:「髪は太いが、分け目の幅が広いことが悩み」）で対応を確認できます。

### 写真の推奨仕様
- 縦長（枠は縦横比 3:4）。横長写真は上下が切れて表示されます
- 幅 800〜1200px 程度あれば十分きれいに表示されます

## 更新の反映（写真を追加したあと）
```bash
git add .
git commit -m "症例写真を追加"
git push
```
push すると Vercel が自動で再デプロイし、数十秒で公開サイトに反映されます。
