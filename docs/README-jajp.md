<h1 align="center">
  <a href="https://standardjs.com"><img src="https://cdn.rawgit.com/standard/standard/master/sticker.svg" alt="Standard - JavaScript Style Guide" width="200"></a>
  <br>
  JavaScript Standard Style
  <br>
  <br>
</h1>

<p align="center">
  <a href="https://travis-ci.org/standard/standard"><img src="https://img.shields.io/travis/standard/standard/master.svg" alt="travis"></a>
  <a href="https://www.npmjs.com/package/standard"><img src="https://img.shields.io/npm/v/standard.svg" alt="npm version"></a>
  <a href="https://www.npmjs.com/package/eslint-config-standard"><img src="https://img.shields.io/npm/dm/eslint-config-standard.svg" alt="npm downloads"></a>
  <a href="https://standardjs.com"><img src="https://img.shields.io/badge/code_style-standard-brightgreen.svg" alt="Standard - JavaScript Style Guide"></a>
</p>

<p align="center">
  <a href="/docs/README-en.md">English</a> •
  <a href="/docs/README-esla.md">Español (Latinoamérica)</a> •
  <a href="/docs/README-fr.md">Français</a> •
  <a href="/docs/README-iteu.md">Italiano (Italian)</a> •
  <a href="/docs/README-jajp.md">日本語 (Japanese)</a> •
  <a href="/docs/README-kokr.md">한국어 (Korean)</a> •
  <a href="/docs/README-ptbr.md">Português (Brasil)</a> •
  <a href="/docs/README-zhcn.md">简体中文 (Simplified Chinese)</a> •
  <a href="/docs/README-zhtw.md">繁體中文 (Taiwanese Mandarin)</a>
</p>

<br>

## JavaScriptスタイルガイドと、校正、フォーマットツール

このモジュールは、次の3つの方法であなたの(そして皆の!)時間を節約します。

- **設定が不要** プロジェクトで一貫性のあるスタイルを適用するための最も簡単な方法です。ただ入れるだけです。
- **自動でコードをフォーマット** `standard --fix` を実行すると、乱雑なコードや一貫性のないコードと別れることができます。
- **スタイルの問題とプログラマのエラーを早期発見** レビュワーとコントリビューターとの間の(無駄な)やり取りを排除することで、貴重なコードレビューの時間を節約します。

作るために決めることはありません。`.eslintrc`や、`.jshintrc`、`.jscsrc`ファイルの管理も不要です。すぐに使うことができます。

インストール方法:

```
npm install standard--save-dev
```

### オープンソースサポーター

[サポーターになろう!](https://feross.org/thanks/)

## StandardJS — ルール

- **2つのスペース** を使用します - インデント
- **Stringにはシングルクォーテーション** を使用します - エスケープを避ける場合を除きます。
- **使用されていない変数を無くす** - これは *大量* のバグを招く原因です。
- **セミコロンを使わない** - [それは][1] [大丈夫][2] [本当に!][3]
  - [詳細][4]
- **キーワードの後に​​スペース** `if（condition）{...}`
- **関数名の後にスペース** `function name（arg）{...}`
- 常に `==`の代わりに `===`を使用します。 - ただし `null || undefined`は `obj == null`で比較しても構いません。
- node.jsで `err`パラメータは、常に処理しなければなりません。
- ブラウザのグローバルを宣言する場合には、ファイルの先頭に `/* global */`を記述します。
  - `open`, `length`, `event`, `name`のような漠然とした名前をブラウザグローバルで偶発的に使用することを防ぎます
  - 例: `/* global alert, prompt */`
  - 例外: `window`, `document`, `navigator`
- **[その他の良いルール][5]** - *さっそく `standard`を試してみてください!*


[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons
[3]: https://www.youtube.com/watch?v=gsfbh17Ax9I
[4]: RULES-jajp.md#semicolons
[5]: RULES-jajp.md#javascript-standard-style

より良いアイデアを得るためには、JavaScript Standard Styleで作成された
[サンプルファイル](https://github.com/expressjs/body-parser/blob/master/index.js)を見てください。または `standard`を使用している
[とてもたくさんのパッケージ](https://raw.githubusercontent.com/standard/standard-packages/master/all.json)の中のいずれかを見てみてください！

## 目次

- クイックスタート
  - [インストール](#インストール)
  - [使い方](#使い方)
  - [理解していたら次にすること](#理解していたら次にすること)
- FAQ
  - [なぜJavaScript Standard Styleを使用するのですか？](#なぜ-JavaScript-Standard-Style-を使用するのですか？)
  - [JavaScript Standard Styleを使うのはどのような人ですか？](#JavaScript-Standard-Style-を使うのはどのような人ですか？)
  - [テキストエディタのプラグインはありますか？](#テキストエディタのプラグインはありますか？)
  - [readmeに入れられるバッジはありますか？](#readmeに入れられるバッジはありますか？)
  - [一致しないルールがあります。変更は可能ですか？](#一致しないルールがあります。変更は可能ですか？)
  - [Web標準ではないではありませんか！](#Web標準ではないではありませんか！)
  - [自動フォーマッターはありますか？](#自動フォーマッターはありますか？)
  - [ファイルを無視するにはどうすればいいですか？](#ファイルを無視するにはどうすればいいですか？)
  - [警告を非表示にするにはどうすればいいですか？](#警告を非表示にするにはどうすればいいですか？)
  - [グローバルnamespaceを汚染させるライブラリを使用します。「variable is not defined」エラーを回避するにはどうすればいいですか？](#グローバルnamespaceを汚染させるライブラリを使用します。「variable-is-not-defined」エラーを回避するにはどうすればいいですか？)
  - [実験版JavaScript(ES Next)の新機能はどのように使用しますか？](#実験版JavaScript-ES-Next-の新機能はどのように使用しますか？)
  - [FlowやTypeScriptのようなJavascript派生言語でも使用することができますか？](#FlowやTypeScriptのようなJavascript派生言語でも使用することができますか？)
  - [Mocha、Jasmine、QUnitなどはどうすればいいですか？](#Mocha、Jasmine、QUnitなどはどうすればいいですか？)
  - [Web WorkesとService Workersはどうすればいいですか？](#Web-WorkesとService-Workersはどうすればいいですか？)
  - [MarkdownまたはHTMLファイル内のコードを確認することができますか？]（＃markdown-または-html-ファイル - 内部の - コードを - 確認 - 数 - か）
  - [Git`pre-commit` hookはありますか？]（＃git-pre-commit-hookが - か）
  - [出力の両方を、華やかできれいに作成するにはどうすればいいですか？]（＃出力を - すべて - カラフルで - きれい - 作成するには - どのように - する必要が - か）
  - [Node.js APIはありますか？]（＃nodejs-apiが - か）
  - [`standard`貢献はどうすればいい？]（＃standard-貢献は - どのように - か）
- [ライセンス]（＃ライセンス）

## インストール

JavaScript Standard Styleを使用する最も簡単な方法は、Nodeコマンドプログラムを介してグローバルにインストールすることです。ターミナルで次のコマンドを実行します。

```bash
$ npm install standard --global
```

または`standard`をローカルにインストールして、単一のプロジェクトで使用することができます。

```bash
$ npm install standard --save-dev
```

*Memo: 上記のコマンドを実行するには、[Node.js]（http://nodejs.org）と[npm]（https://npmjs.com）がインストールされている必要があります。*

## 使い方

`standard`をインストールした後、`standard`プログラムを使用することができます。最も簡単な使用例は、現在の作業ディレクトリにあるすべてのJavaScriptファイルのスタイルを確認することです。

```bash
$ standard
Error: Use JavaScript Standard Style
  lib/torrent.js:950:11: Expected '===' and instead saw '=='.
```

globパターンを使用して任意のディレクトリを渡すことができます。globパターンを含むパスは、シェルではなく`standard`によって展開されるように、引用符で囲んでください。

```bash
$ standard "src/util/**/*.js" "test/**/*.js"
```

**メモ** 基本的に`standard`は、次のパターンと一致するすべてのファイルを検索しています:
`**/*.js`, `**/*.jsx`

## 理解していたら次にすること

1. `package.json`に次のコードを追加します。

```json
{
  "name": "my-cool-package",
  "devDependencies": {
    "standard": "*"
  },
  "scripts": {
    "test": "standard && node my-tests.js"
  }
}
```

2. `npm test`を実行すると、自動的にスタイルがチェックされます。

  ```bash
  $ npm test
  Error: Use JavaScript Standard Style
    lib/torrent.js:950:11: Expected '===' and instead saw '=='.
  ```

3. これでプルリクエストにスタイルのフィードバックをすることは二度とありません!

## なぜJavaScript Standard Styleを使用するのですか？

JavaScript Standard Styleの利点は、シンプルであることです。モジュールやプロジェクトごとの数百行のスタイル設定ファイルを、誰もメンテナンスしたくはないでしょう。それは狂気の沙汰です。

このモジュールは、次の3つの方法であなたの(そして皆の!)時間を節約します。

- **設定が不要** プロジェクトで一貫性のあるスタイルを適用するための最も簡単な方法です。ただ入れるだけです。
- **自動でコードをフォーマット** `standard --fix` を実行すると、乱雑なコードや一貫性のないコードと別れることができます。
- **スタイルの問題とプログラマのエラーを早期発見** レビュワーとコントリビューターとの間の(無駄な)やり取りを排除することで、貴重なコードレビューの時間を節約します。

`standard`スタイルを採用することは、個人的なスタイルよりも、コードの明瞭性とコミュニティの慣習を優先することを意味します。これは、100%のプロジェクトや開発における文化に合理的とは言えないかもしれません。しかしながらオープンソースは、初心者にとって好ましくない場所になることがあります。明瞭化と自動化を行ったコントリビューターの割合は、プロジェクトをより健康的にするでしょう。

## JavaScript Standard Styleを使うのはどのような人ですか？

多くの人々が使っています!

[<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/npm.png>](https://www.npmjs.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/github.png>](https://github.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/opbeat.png>](https://opbeat.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/nearform.png>](http://www.nearform.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/brave.png>](https://www.brave.com) |
|---|---|---|---|---|

| [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/zeit.png>](https://zeit.co) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/zendesk.png>](https://www.zendesk.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/mongodb.jpg>](https://www.mongodb.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/typeform.jpg>](https://www.typeform.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/gov-uk.png>](https://gds.blog.gov.uk) |
|---|---|---|---|---|

[<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/express.png>](http://expressjs.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/webtorrent.png>](https://webtorrent.io) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/ipfs.png>](https://ipfs.io) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/dat.png>](https://datproject.org) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/bitcoinjs.png>](https://bitcoinjs.org) |
|---|---|---|---|---|

[<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/atom.png>](https://atom.io) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/electron.png>](http://electron.atom.io) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/voltra.png>](https://voltra.co) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/treasuredata.png>](https://www.treasuredata.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/clevertech.png>](https://clevertech.biz) |
|---|---|---|---|---|

[<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/studynotes.jpg>](https://www.apstudynotes.org) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/optiopay.png>](https://www.optiopay.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/jaguar-landrover.png>](https://www.jlrtechincubator.com/jlrti/) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/bustle.jpg>](https://www.bustle.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/zentrick.png>](https://www.zentrick.com) |
|---|---|---|---|---|

[<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/nodesource.png>](https://nodesource.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/greenkeeper.png>](https://greenkeeper.io) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/karma.png>](https://karma-runner.github.io) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/taser.png>](https://www.taser.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/neo4j.png>](https://www.neo4j.com) |
|---|---|---|---|---|

[<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/rentograph.png>](https://rentograph.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/eaze.png>](https://www.eaze.com) | [<img width=150 src=https://cdn.rawgit.com/standard/standard/master/docs/logos/ctrl-alt-deseat.png>](https://www.ctrlaltdeseat.com) | | |
|---|---|---|---|---|

会社以外の多くのコミュニティのメンバーが、ここに記載した[とてもたくさんのパッケージ](https://raw.githubusercontent.com/standard/standard-packages/master/all.json)で`standard`を使っています。

また`standard`は、GitHubの[Clean Code Linter](https://github.com/showcases/clean-code-linters)ショーケースで首位のlinterです。

## テキストエディタのプラグインはありますか？

まず、`standard`をインストールします。その後、エディタに適切なプラグインをインストールしてください。

### Sublime Text

**[Package Control][sublime-1]** を使用して、 **[SublimeLinter][sublime-2]** と **[SublimeLinter-contrib-standard][sublime-3]** をインストールします。

保存時に自動的にフォーマットを適用するには、 **[StandardFormat][sublime-4]** をインストールしてください。

[sublime-1]: https://packagecontrol.io/
[sublime-2]: http://www.sublimelinter.com/en/latest/
[sublime-3]: https://packagecontrol.io/packages/SublimeLinter-contrib-standard
[sublime-4]: https://packagecontrol.io/packages/StandardFormat

### Atom

**[linter-js-standard][atom-1]** をインストールします。

または **[linter-js-standard-engine][atom-4]** をインストールすることもできます。その場合、バンドルされたバージョンの `standard`の代わりに、現在のプロジェクトにインストールされたバージョンを自動的に使用します。また **[standard-engine][atom-5]** をベースにした他のlinterでも動作します。

自動的にフォーマットを適用するには、 **[standard-formatter][atom-2]** をインストールします。スニペットの場合 **[standardjs-snippets][atom-3]** をインストールします。

[atom-1]: https://atom.io/packages/linter-js-standard
[atom-2]: https://atom.io/packages/standard-formatter
[atom-3]: https://atom.io/packages/standardjs-snippets
[atom-4]: https://atom.io/packages/linter-js-standard-engine
[atom-5]: https://github.com/Flet/standard-engine

### Visual Studio Code

**[vscode-standardjs][vscode-1]** をインストールします。(自動フォーマットをサポートします。)

JSスニペットの場合は **[vscode-standardjs-snippets][vscode-2]** をインストールします。Reactスニペットの場合は **[vscode-react-standard][vscode-3]** をインストールします。

[vscode-1]: https://marketplace.visualstudio.com/items/chenxsan.vscode-standardjs
[vscode-2]: https://marketplace.visualstudio.com/items?itemName=capaj.vscode-standardjs-snippets
[vscode-3]: https://marketplace.visualstudio.com/items/TimonVS.ReactSnippetsStandard

### Vim

**[ale][vim-1]** をインストールし、次のコードを`.vimrc`に追加します。

```vim
let g:ale_linters = {
\   'javascript': ['standard'],
\}
let g:ale_fixers = {'javascript': ['standard']}
```

これは、eslintとの衝突を避け、`standard`をjavascriptファイル用の唯一のlinterおよびfixerとして設定します。保存時に自動的にフォーマットを適用するには、次のコードを`.vimrc`に追加します。
```vim
let g:ale_lint_on_save = 1
let g:ale_fix_on_save = 1
```

考えられる代替プラグインとしては、[neomake][vim-2]と[syntastic][vim-3]があり、両方とも`standard`のサポートが組み込まれています。(追加設定が必要になる場合があります)

[vim-1]: https://github.com/w0rp/ale
[vim-2]: https://github.com/neomake/neomake
[vim-3]: https://github.com/vim-syntastic/syntastic

### Emacs

**[Flycheck][emacs-1]** をインストールして、**[manual][emacs-2]** を見てプロジェクトでこれを有効にする方法を確認してください。

[emacs-1]: http://www.flycheck.org
[emacs-2]: http://www.flycheck.org/en/latest/user/installation.html

### Brackets

extension registryで **["Standard Code Style"][brackets-1]** を検索して「Install」をクリックします。

[brackets-1]: https://github.com/ishamf/brackets-standard/

### WebStorm（PhpStorm、IntelliJ、RubyMine、JetBrains、etc.）

WebStromは`standard`がIDEで直接使用可能と[標準サポートに関する発表](https://blog.jetbrains.com/webstorm/2017/01/webstorm-2017-1-eap-171-2272/)をしました。

もし、手動で`standard`を構成するには、[ガイド]([webstorm-1])を参照してください。PhpStorm、IntelliJ、RubyMineなど、すべてのJetBrains製品は同様です。

[webstorm-1]: docs/webstorm.md

## readmeに入れられるバッジはありますか？

Yes! プロジェクトで`standard`を使用する場合、readmeにバッジのいずれかを入れて、コードがstandardスタイルを使用していることを人々に知らせることができます。

[![JavaScript Style Guide](https://cdn.rawgit.com/standard/standard/master/badge.svg)](https://github.com/standard/standard)

```md
[![JavaScript Style Guide](https://cdn.rawgit.com/standard/standard/master/badge.svg)](https://github.com/standard/standard)
```

[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

```md
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
```

## 一致しないルールがあります。変更は可能ですか？

No. `standard`の大きなポイントは、コードスタイルの[自転車置場の議論][自転車置場の議論]を避けることによって、時間を節約することです。タブとスペースなどについては、オンラインで多くの議論があり、解決されることはないでしょう。これらの議論は、何かを得るときに邪魔をします。最終的には '何かを選ぶ' 必要があり、それが `standard`の哲学のすべてです。'何かを選ぶ' 賢明な意見の集合体です。場合によっては、ユーザーが自分の意見を守る上での価値を見つけるでしょう。

何百ものESLintルールを個別に構成する場合、`eslint`を直接
[eslint-config-standard](https://github.com/standard/eslint-config-standard)と一緒に使用して変更を一番上に配置することがすることができます。
[`standard-eject`](https://github.com/josephfrazier/standard-eject)は、`standard`から`eslint`と` eslint-config-standard`への移行を支援することができます。

ヒント: `standard`を使用し実行すれば、あなたの時間を消費している現実的な問題が解決します! :P

[自転車置場の議論]: https://www.freebsd.org/doc/en/books/faq/misc.html#bikeshed-painting

## Web標準ではないではありませんか！

もちろん、標準ではありません！ここで提示されたスタイルは、公式Web標準のグループと関連がないので、`ECMA/standard`ではなく、`standard/standard`というリポジトリになっています。

「standard」という言葉は、「web standard」以上の意味を持っています :-)

例えば:
- このモジュールは、私たちのコードをハイレベル *standard品質* に維持するのに役立ちます。
- このモジュールは、新しいコントリビューターが基本的な *standardスタイル* に準拠するようにします。

## 自動フォーマッターはありますか？

Yes! `standard --fix`を使用することで、ほとんどの問題を自動的に修正することができます。

`standard --fix`は最高の利便性のために`standard`に内蔵されています。ほとんどの問題が修正できますが、いくつかのエラー(エラー処理を忘れてしまうようなこと)は、手動で修正する必要があります。

時間節約のために、`standard`は自動的に変更できる問題を発見すると、「`Run standard --fix to automatically fix some problems`」メッセージを出力します。

## ファイルを無視するにはどうすればいいですか？

特定のパス (`node_modules/`, `coverage/`, `vendor/`, `*.min.js`, `bundle.js`と、`.git/`のように`.`で始まるファイル/フォルダ) は自動的に無視されます。

プロジェクトのルートの`.gitignore`ファイルに記述されたパスも自動的に無視されます。

追加フォルダや特定の最小化ファイルを無視したいことがあります。これを行うには、`package.json`に`standard.ignore`属性を追加します。

```json
"standard": {
  "ignore": [
    "**/out/",
    "/lib/select2/",
    "/lib/ckeditor/",
    "tmp.js"
  ]
}
```

## 警告を非表示にするにはどうすればいいですか？

まれに、規則に違反して `standard`によって生成された警告を非表示にする必要があります。

JavaScript Standard Styleは[ESLint](http://eslint.org/)を使用しており、ESLintを直接使用した場合、一般的に、警告を非表示にすることができます。

詳細な出力を得るために(無視する特定のルール名を見つけることができるように)、以下を実行します。

```bash
$ standard --verbose
Error: Use JavaScript Standard Style
  routes/error.js:20:36: 'file' was used before it was defined. (no-use-before-define)
```

特定の行で **すべてのルール** を無効にすることができます。

```js
file = 'I know what I am doing' // eslint-disable-line
```

あるいは、特定の行で `"no-use-before-define"`ルール **のみ** 無効にすることができます。

```js
file = 'I know what I am doing' // eslint-disable-line no-use-before-define
```

あるいは、 **複数の行** で `"no-use-before-define"`ルールを無効にすることができます。

```js
/* eslint-disable no-use-before-define */
console.log('offending code goes here...')
console.log('offending code goes here...')
console.log('offending code goes here...')
/* eslint-enable no-use-before-define */
```

## グローバルnamespaceを汚染させるライブラリを使用します。「variable is not defined」エラーを回避するにはどうすればいいですか？

いくつかのパッケージ(例えば、`mocha`)は、関数(例えば、`describe`, `it`)をグローバルオブジェクトに配置します(悪い形!)。これらの関数が定義されていないか、コードのどこかで`require`されていない間、`standard`は定義されていない変数を使用していると警告します(一般的には、このルールは、タイプミスをキャッチするために役立ちます)。しかし、これらのグローバル変数については、エラーを無効にしたいところです。

`standard`(だけでなくコードを読んでいる人)が、特定の変数がコード内でグローバルであることがわかるように、以下のコードをファイルの先頭に追加してください。

```js
/* global myVar1, myVar2 */
```

もしも数百個のファイルがある場合は、すべてのファイルにコメントを追加したくはないと思います。その場合は、次のコードを実行します。

```bash
$ standard --global myVar1 --global myVar2
```

あるいは`package.json`に次のコードを追加します。

```json
{
  "standard": {
    "globals": [ "myVar1", "myVar2" ]
  }
}
```

*Note: `global`と`globals`は同じです。*

## 実験版JavaScript(ES Next)の新機能はどのように使用しますか？

`standard`は提案プロセスの「Stage 4」にある言語機能の提案を含む、最新のECMAScript ES8(ES2017)の新機能をサポートします。

実験版の言語機能をサポートするために、`standard`はカスタムJavaScriptパーサの指定をサポートします。カスタムパーサーを使用する前に、追加された複雑さがそれに値するかどうかを考慮してください。

カスタムパーサーを使用するには、npmモジュールをインストールします。

```bash
npm install babel-eslint --save-dev
```

そして次のコードを実行します。

```bash
$ standard --parser babel-eslint
```

あるいは、`package.json`に次のコードを追加します。

```json
{
  "standard": {
    "parser": "babel-eslint"
  }
}
```

`standard`がグローバルにインストールされている場合(つまり、`npm install standard --global`)、`babel-eslint`も同様に`npm install babel-eslint --global`としてグローバルにインストールしてください。

## FlowやTypeScriptのようなJavascript派生言語でも使用することができますか？

`standard`は、最新のECMAScriptの機能をサポートします。しかし、FlowやTypeScriptは新しい構文を言語に追加しているため、すぐに使用することができません。

JavaScript派生言語をサポートするために、`standard`は変更された構文を処理するESLintプラグインだけでなく、カスタムJavaScriptパーサの指定をサポートします。 JavaScript派生言語を使用する前に、追加された複雑さがそれに値するかどうかを考慮してください。

### Flow

Flowを使用するには、 `babel-eslint`をパーサとして、`eslint-plugin-flowtype`をプラグインとして`standard`を実行する必要があります。

```bash
npm install babel-eslint eslint-plugin-flowtype --save-dev
```

そして次のコードを実行します。

```bash
$ standard --parser babel-eslint --plugin flowtype
```

あるいは、`package.json`に次のコードを追加します。

```json
{
  "standard": {
    "parser": "babel-eslint",
    "plugins": [ "flowtype" ]
  }
}
```

*Note: `plugin`と`plugins`は同じです。*

`standard`がグローバルにインストールされている場合(つまり、`npm install standard --global`)、`babel-eslint`と`eslint-plugin-flowtype`も同様に、`npm install babel-eslint eslint-plugin-flowtype --global`としてグローバルにインストールしてください。

### TypeScript

TypeScriptを使用するには、`typescript-eslint-parser`をパーサとして、`eslint-plugin-typescript`をプラグインとして、`*.ts`ファイルを標準に含めるものとしてlintに渡します。(デフォルトではないため)

```bash
npm install typescript-eslint-parser eslint-plugin-typescript --save-dev
```

そして次のコードを実行します。

```bash
$ standard --parser typescript-eslint-parser --plugin typescript *.ts
```

あるいは、`package.json`に次のコードを追加します。

```json
{
  "standard": {
    "parser": "typescript-eslint-parser",
    "plugins": [ "typescript" ]
  }
}
```

`package.json`を使用する場合、以下のコードを実行します。

```bash
standard *.ts
```

`standard`がグローバルにインストールされている場合(つまり、`npm install standard --global`)、`typescript-eslint-parser`と`eslint-plugin-typescript`も同様に、`npm install typescript-eslint-parser eslint-plugin-typescript --global`としてグローバルにインストールしてください。

## Mocha、Jasmine、QUnitなどはどうすればいいですか？

テストファイルでmochaをサポートするには、テストファイルの先頭に次のコードを追加します。

```js
/* eslint-env mocha */
```

あるいは、次のコードを実行します。

```bash
$ standard --env mocha
```

`mocha`は`jasmine`, `qunit`, `phantomjs`などのいずれか1つになります。全てのリストは、ESLintの[specifying environments](http://eslint.org/docs/user-guide/configuring.html#specifying-environments)を確認しください。これらの環境のうちグローバルで使用できるもののリストは、[globals](https://github.com/sindresorhus/globals/blob/master/globals.json) npmモジュールを確認してください。

*Note: `env`と`envs`は同じです。*

## Web WorkesとService Workersはどうすればいいですか？

Web Workerファイルの先頭に次のコードを追加します。

```js
/* eslint-env worker */
```

`standard`(だけでなくコードを読んでいる人)が、`self`がWeb Workerのコード内でグローバルであることがわかるようになります。

Service Workerでは、次のようになります。

```js
/* eslint-env serviceworker */
```

## MarkdownまたはHTMLファイル内のコードを確認することができますか？

Markdownファイル内のコードを確認するには、[ `standard-markdown`]（https://www.npmjs.com/package/standard-markdown）を使用してください。

またはMarkdown、HTML、および他の多くの種類の言語ファイルのコードを確認することができるESLintプラグインがあります。

Markdownファイル内のコードを確認するには、ESLintプラグインを使用してください。

```bash
$ npm install eslint-plugin-markdown
```

その後、コードブロック内のJSを確認するには、以下を実行してください。

```bash
$ standard--plugin markdown」**/*。md」
```

HTMLファイル内のコードを確認するには、ESLintプラグインを使用してください。

```bash
$ npm install eslint-plugin-html
```

その後、`<script>`タグ内にあるJSを確認するには、以下を実行してください。

```bash
$ standard--plugin html」**/*。html」
```

## Git `pre-commit` hookはありますか？

面白い質問ですね！

`` `bash
＃！/ bin / bash

＃コミットのために準備されたすべてのJavaScriptファイルは、標準コードのスタイルを通過することを確認します。
function xargs-r（）{
  ＃Portable version of "xargs -r" The -r flag is a GNU extension that
  ＃prevents xargs from running if there are no input files。
  if IFS = read -r -d $ '\ n' path; then
    {echo "$ path"; cat; } | xargs $ @
  fi
}
git diff --name-only --cached --relative | grep '\ .jsx \？$' | sed 's / [^ [：alnum：]] / \\＆/ g' | xargs-r -E '' -t standard
if [[$？ -ne 0]]; then
  echo 'JavaScript Standard Style errors were detected。 Aborting commit」
  exit 1
fi
`` `

##出力の両方を、華やかで*きれい*作成するにはどうすればいいですか？

内蔵された出力は、シンプルで簡単ですが、輝くものにしたい場合、[snazzy]（https://www.npmjs.com/package/snazzy）インストールしてください。

`` `bash
$ npm install snazzy
`` `

そして次のコマンドを実行します。

`` `bash
$ standard --verbose | snazzy
`` `

[standard-tap](https://www.npmjs.com/package/standard-tap),
[standard-json](https://www.npmjs.com/package/standard-json),
[standard-reporter](https://www.npmjs.com/package/standard-reporter),
[standard-summary](https://www.npmjs.com/package/standard-summary)도 있습니다..

## Node.js APIはありますか？

はい！

### standard.lintText（text、[opts]、callback）`

リントに提供するソース`text`を準備します。`opts`オブジェクトを追加することができます。

```js
{
  cwd：''、//現在の作業ディレクトリ（デフォルト：process.cwd（））
  filename：''、//リントテキストを含むファイルへのパス（選択すると、いくつかのeslintプラグインが必要）
  fix：false、//自動トラブルシューティング
  globals：[]、//宣言するカスタムグローバル変数
  plugins：[]、//カスタムeslintプラグイン
  envs：[]、//カスタムeslint環境
  parser：''//カスタムjsパーサー（例えば、babel-eslint）
}
```

`package.json`が現在の作業ディレクトリで見つかった場合、追加のオプションを読み込むことができます。

`コールバック（callback）`は`Error`と` results`オブジェクトと一緒に呼び出されています。

`results`オブジェクトは、次のような属性が含まれています。

```js
var results={
  results：[
    {
      filePath：''、
      messages：[
        {ruleId：''、message：''、line：0、column：0}
      ]、
      errorCount：0、
      warningCount：0、
      output：''//固定のソースコード（{fix：true}オプションと一緒に提供される）
    }
  ]、
  errorCount：0、
  warningCount：0
}
```

### results= standard.lintTextSync（text、[opts]）`

`standard.lintText（）`の同期バージョン。エラーが発生した場合、例外が発生します。そうでなければ`results`オブジェクトが返されます。

### standard.lintFiles（files、[opts]、callback）`

指定された「files」の塊をリントに適用することができます。`opts`オブジェクトを追加することができます。

```js
var opts={
  ignore：[]、//ファイルの束を無視します。（基本的な無視ファイルが含まれています）
  cwd：''、//現在の作業ディレクトリ（デフォルト：process.cwd（））
  fix：false、//自動トラブルシューティング
  globals：[]、//宣言するグローバル変数
  plugins：[]、// eslintプラグイン
  envs：[]、// eslint環境
  parser：''// jsパーサー（例えば、babel-eslint）
}
```

`callback`は` Error`と `results`オブジェクトに呼び出されます。（上記です）

## `standard`貢献はどうすればいい？

貢献を歓迎します！ [issues]（https://github.com/standard/standard/issues）や[PRs]（https://github.com/standard/standard/pulls）を確認し、そこに見えないことをしたい場合は、直接作ってください。

チャットをご希望ですか？ freenodeの `＃standard`チャンネルでIRCの参加者と一緒にしてください。

以下は、 `standard`生態系の重要なパッケージです。

- ** [standard]（https://github.com/standard/standard）** - 現在のストレージ
   - ** [standard-engine]（https://github.com/flet/standard-engine）** - 任意のeslintルールのcliエンジン
   - ** [eslint-config-standard]（https://github.com/standard/eslint-config-standard）** - `standard`のeslintルール
   - ** [eslint-config-standard-jsx]（https://github.com/standard/eslint-config-standard-jsx）** - `standard`のeslint規則（JSX）
   - ** [eslint-plugin-standard]（https://github.com/xjamundx/eslint-plugin-standard）** - `standard`のためのカスタムeslint規則（eslintコアの一部がありません。）
   - ** [eslint]（https://github.com/eslint/eslint）** - 強力なstandard linter
- ** [snazzy]（https://github.com/standard/snazzy）** - standardをきれいに端末に出力できます。
- ** [standard-www]（https://github.com/standard/standard-www）** - https://standardjs.comのコード
- ** [semistandard]（https://github.com/Flet/semistandard）** - セミコロンが含まれているstandard（必要な場合）

また、多くの** [エディタプラグイン]（＃text-editor-plugins）**、** [ `standard`を使用するnpmパッケージリスト]（https://github.com/standard/standard-packages）**、 ** [ `standard`エコシステムの素敵なパッケージのリスト]（https://github.com/standard/awesome-standard）**があります。

##ライセンス

[MIT](LICENSE). Copyright (c) [Feross Aboukhadijeh](http://feross.org).
