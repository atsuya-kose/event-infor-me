# 東京周辺 おでかけイベント

家族向け・グルメのイベントをまとめた静的サイトです(GitHub Pagesで公開)。

## 構成
- `index.html` … 表示ページ(絞り込み: 家族/グルメ、今週末/開催中、エリア)
- `events.js` … イベントデータ。**更新するのはこのファイルだけ**
- 終了日を過ぎたイベントは自動で非表示になります

## 公開方法(GitHub Pages)
1. リポジトリの Settings → Pages
2. Source: `Deploy from a branch` / Branch: `main` / Folder: `/ (root)`
3. 数分後に `https://<ユーザー名>.github.io/<リポジトリ名>/` で閲覧できます

## 週次更新の手順
Claudeに「東京周辺のイベント情報を更新して」と依頼すると、`events.js` の追加・修正と `LAST_UPDATED` の更新を行います。
手動で更新する場合は `events.js` の `EVENTS` に項目を追加してください。

```js
{
  id: "一意のID",
  title: "イベント名",
  start: "2026-11-14", end: "2026-11-15",   // 終了日が不明なら null
  area: "東京",                              // 東京/神奈川/埼玉/千葉
  venue: "会場名(区市)",
  price: "料金",
  categories: ["family", "gourmet"],         // どちらか、または両方
  summary: "見どころ",
  url: "出典URL", source: "出典名"
}
```

## 注意
- 掲載情報は各出典ページに基づきます。開催日・料金・予約要否は変更されることがあるため、お出かけ前に公式サイトで確認してください。
- リポジトリを公開(public)にすると、サイトも誰でも閲覧できます。
