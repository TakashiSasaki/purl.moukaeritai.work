# Repository Rules

このリポジトリは GitHub Pages 上で `purl.moukaeritai.work` として公開され、`purl.org` および `purl.archive.org` からの転送先として使われる。

## Routing Policy

- トップページ `/` の canonical URL は `https://purl.moukaeritai.work/` である。
- `/` は `https://purl.org/` へ即時リダイレクトする。
- `/gag`、`/get-a-grip`、`/ts` はそれぞれ `https://purl.org/gag/`、`https://purl.org/get-a-grip/`、`https://purl.org/ts/` へリダイレクトする。
- それ以外の存在しないパスは `404.html` を表示する。

## 404 Handling

- `404.html` は JavaScript で現在の `location.pathname`、`location.search`、`location.hash` を読み取り、`https://purl.org` をオーソリティにした候補URLを組み立てて表示する。
- 404 画面では、その候補URLをリンクとして見せ、コピーしやすい形にする。
- `purl.archive.org` 由来のリクエストでも、案内先は `purl.org` を正とする。

## Maintenance Notes

- このサイトには実質的なコンテンツを増やさず、リダイレクトと案内に集中する。
- ルーティング方針を変えるときは、`index.html`、各サブディレクトリの `index.html`、`404.html` をまとめて見直す。
- 仕様が増えたら、このファイルに追記して次の作業者が同じ前提で動けるようにする。
