# 散歩（仮） 作品サイト

スマホ対応の縦スクロール漫画サイト。フレームワーク・有料サービス不要。

## まず公開する（GitHub Pages）

1. GitHubにログインし、New repository から **`sanpo-site`** という名前の **Public** リポジトリを作る。
2. このフォルダの中身（`index.html`, `style.css`, `chapters/`, `images/`）をリポジトリのルートにアップロードしてコミットする。ZIPをそのままアップロードするのではなく、解凍して中身をアップロードする。
3. リポジトリの **Settings → Pages → Build and deployment** で **Deploy from a branch** を選ぶ。
4. Branch を **main**、フォルダを **/(root)** にして **Save**。
5. 数分後、`https://あなたのユーザー名.github.io/sanpo-site/` で閲覧できる。反映まで時間がかかる場合あり。

## 漫画の画像を入れる

1. `images/` に画像を置く（例：`01-001.webp`, `01-002.webp`）。PNG/JPGも可。
2. `chapters/01.html` の `<main class="reader">` と `</main>` の間にある仮の `<div class="sample-panel"> ... </div>` をすべて削除。
3. 代わりに次のように並べる。画像の高さは自由。上下に隙間なくつながる。

```html
<img class="panel" src="../images/01-001.webp" alt="第1話 1枚目">
<img class="panel" src="../images/01-002.webp" alt="第1話 2枚目" loading="lazy">
<img class="panel" src="../images/01-003.webp" alt="第1話 3枚目" loading="lazy">
```

4. GitHub上で変更をコミットすればサイトも自動更新される。

## 新しい話を追加する

`chapters/01.html` をコピーして `02.html` にし、タイトル・画像を変更。`index.html` の EPISODES に第2話へのリンクを追加。

## メモ

- 画像は1枚に結合しなくてOK。縦に並べるだけでウェブトゥーン風になる。
- 画像は表示速度のため WebP 推奨。幅 800〜1200px 程度を目安に、細かい文字が読めるかスマホで確認。
- 作品名、説明文、著作権表記はすべて仮置き。好きに変更可能。
- GitHub Pagesは静的サイト向け。無料利用には利用条件と制限がある。
