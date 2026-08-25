# 週次美容業界動向レポート サイト

美容室・美容業界の最新動向を週次でまとめた静的サイトです。GitHub Pagesでの公開を想定しています。

```
beauty-industry-weekly-site/
├── index.html              ← アーカイブ一覧ページ（トップページ）
├── reports/
│   └── beauty-weekly-2026-08-25.html   ← 各週のレポート本体
└── README.md
```

---

## 1. GitHub Desktopでリポジトリを作る

1. GitHub Desktopを開き、上部メニューから **File → New Repository** を選択
2. Name に `beauty-industry-weekly-site`（好きな名前でOK）を入力
3. Local Path で、このフォルダ一式を置きたい場所を選択
4. **Create Repository** をクリック
5. このフォルダの中身（`index.html` / `reports/` / `README.md`）を、作成されたリポジトリのフォルダに丸ごとコピー
6. GitHub Desktop左下に変更差分が表示されるので、下部の Summary 欄に「初回コミット」などと入力し **Commit to main**
7. 右上の **Publish repository** をクリック（Publicにチェックを入れると後述のGitHub Pagesが使えます）

## 2. GitHub Pagesで公開する

1. GitHub.com上で、Publishしたリポジトリのページを開く
2. **Settings → Pages** を開く
3. Source を「Deploy from a branch」、Branch を「main」／フォルダを「/ (root)」に設定して **Save**
4. 数分後、`https://ユーザー名.github.io/beauty-industry-weekly-site/` でサイトが公開されます

---

## 3. 毎週レポートを追加する手順

新しいレポートができたら、以下の3ステップだけでサイトが更新されます。

1. 新しく生成された `beauty-weekly-YYYY-MM-DD.html` を `reports/` フォルダに追加
2. `index.html` の `<div class="archive-list">` 内に、以下のカードを**一番上**に追加し、直前の最新号カードから `latest` クラスと `<span class="badge">最新号</span>` を外す（1つ前の号として残す）

```html
<a class="archive-card latest" href="reports/beauty-weekly-YYYY-MM-DD.html">
  <div class="info">
    <span class="badge">最新号</span>
    <h2>（今週の見出しサマリーをここに）</h2>
    <div class="period">YYYY年M月D日 〜 M月D日 ｜ 全7件</div>
  </div>
  <div class="arrow">→</div>
</a>
```

3. GitHub Desktopで変更を確認し、Commit → Push するだけで公開サイトに反映されます

※ Claudeに「今週のレポートを作って、サイトのindex.htmlに追加するカードのコードも出して」と頼めば、上記の差し込み用HTMLも一緒に用意できます。

---

## デザインについて

`reports/` 内の各レポートも `index.html` も、グラスモーフィズム×ローズゴールドの統一デザインです。今後のレポート作成時も、既存の `reports/beauty-weekly-2026-08-25.html` の構造をそのまま複製し、中身（見出し・要約・出典）だけ差し替えることをおすすめします（CSSの調整はテスト済みのため、構造を変えると表示崩れの原因になります）。
