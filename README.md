# rscss2e

大規模開発に耐える CSS 構成案

## 基本原則

[FLOCSS](https://github.com/hiloki/flocss) を基本とし子要素以下を [RSCSS](https://rscss.io/) で記述する

## 独自規則
- フォルダ・ファイル・スタイルは [ローワーキャメルケース](https://ja.wikipedia.org/wiki/%E3%82%AD%E3%83%A3%E3%83%A1%E3%83%AB%E3%82%B1%E3%83%BC%E3%82%B9) で記述する
- 親要素はアルファベット小文字1文字 + ハイフンの prefix をつける
- 親要素以外ではハイフンを使わない
- Object フォルダ下のフォルダは上階層に移動し Object フォルダは使用しない
- [深いネスト](https://rfs.jp/sb/html-css/html-css-guide/rscss.html#i-19) は極力避けるも許容する
- Utility・Helpers は使わず [バリアント](https://rfs.jp/sb/html-css/html-css-guide/rscss.html#i-6) で対応
- [NuxtJS](https://nuxtjs.org/) などのフレームワークではページ・コンポーネント内に scoped で記述するのを優先させ Layout・Project は使わない

## ファイル・ディレクトリ構成

### CSS （scss の例）

| | | | 備考 | prefix |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| style/ | component/ | * | component |  c- | 
| | foundation/ | \_base.scss | reset 補完 | |
| | | \_mixin.scss | mixin | |
| | | \_reset.scss | reset css | |
| | | \_variable.scss | 変数 | |
| | layout/ | * | NuxtJS などでは使わない | l- |
| | plugin/ | * | plugin css 上書き | |
| | project/ | * | NuxtJS などでは使わない | p- |
| | \_styleResources.scss | | NuxtJS などのテンプレートで使用する css をまとめたもの | |
| | common.scss | | css を import | |

### ページ・コンポーネント（NuxtJS + [アトミックデザイン](https://atomicdesign.bradfrost.com/) の例）

| | | | | prefix |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| app/ | componets/ | atoms/ | * | a- |
| | | molecules/ | * | m- |
| | | organismas/ | * | o- |
| | layouts/ | * | | l- |
| | pages/ | * | | p- |

## rscss2e とは
[echizenya](https://twitter.com/h_echizenya) & egawa の二人の e で考えたので rscss2e と仮称しています

## テンプレート
こちらまだ README.md だけですがテンプレートみたいなものをコミット予定です

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
