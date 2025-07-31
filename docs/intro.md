---
sidebar_position: 1
---

# Docusaurus 勉強会資料

## 目次
- Docusaurusとは
- インストール方法
- ナビゲーションバーのカスタマイズ
- フッターのカスタマイズ
- テーマの編集

## Docusaurusとは
Metaが管理するReactベースのSSG（Static Site Generator）

Markdownやそれを拡張したMDXでドキュメントやブログを作成できる

## インストール方法

[Docusaurus](https://docusaurus.io/docs)

```markdown
npx create-docusaurus@latest my-website classic
```

`my-website`はフォルダ名
`classic`はテンプレート名

ローカルでの実行
```markdown
npm start
```

## ナビゲーションバーのカスタマイズ
docusaurus.config.ts(or .js)の 

```markdown
config/themeConfig/navbar
```
を見る

title: サイトのタイトル（navbar左側）  
logo: サイトのロゴ（navbar左側）  
items: navbarに表示するコンテンツ

### itemsの中身
itemsの初期状態でのコンテンツは

- [ドキュメント](https://docusaurus.io/docs/api/themes/configuration#navbar-doc-sidebar)
- ブログ(リンク)
- [リンク](https://docusaurus.io/docs/api/themes/configuration#navbar-link)

### ドキュメント
sidebarId: sidebar.tsで設定したID

### リンク
ブログの表示もリンクと同様の仕組み  
to: プロジェクト内のファイルを指定  
href: 外部URLを指定  

### ドロップダウンの作り方
単純な話`items[]`の内部に`items[]`を作ってあげればOK

## フッターのカスタマイズ
ナビゲーションバーのリンク関連のカスタマイズとほぼ一緒

## テーマの編集
テーマは基本的に`node_modules`内に記載されていて変更したくはない
そんな時に使用できるのが[スウィズリング](https://docusaurus.io/docs/swizzling)

スウィズリングを行うと `node_modules`内のテーマに関するファイルを`src`配下にコピーしてくれる

公式ドキュメントでの一例
```markdown
npm run swizzle @docusaurus/theme-classic Footer -- --wrap
```

基本的にDocusaurusの仕様として、 `node_modules`より`src`を優先してくれるようになっているためそこからテーマを編集できる