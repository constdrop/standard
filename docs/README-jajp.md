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
  <a href="/docs/README-kokr.md">한국어 (Korean)</a> •
  <a href="/docs/README-ptbr.md">Português (Brasil)</a> •
  <a href="/docs/README-zhcn.md">简体中文 (Simplified Chinese)</a> •
  <a href="/docs/README-zhtw.md">繁體中文 (Taiwanese Mandarin)</a>
</p>

<br>

##校正及び自動コード修正を助けてくれるJavaScriptスタイルガイド

このモジュールは、次の3つの方法で時間を節約することができます。

- **環境設定が必要ありません。**プロジェクトで一貫性のあるスタイルを適用するための最も簡単な方法です。ただ入れるだけです。
- **自動的にコードフォーマットを合わせています。**`standard--fix`を実行すると、汚れたり、一貫性のないコードとの別れすることができます。
- **スタイル問題とプログラマのエラーを早期に把握することができます。**レビューと貢献の間の関係を削除することにより、貴重なコードレビュー時間を節約することができます。

作ることのために決定する必要がありません。`.eslintrc`、`.jshintrc`、`.jscsrc`ファイルを管理する必要がなく、すぐに可能です。


インストールする方法です。

```
npm install standard--save-dev
```

##ルール

- ** 2カーンのスペースを使用します。** - インデント
- **文字列に単一引用符を使用します。** - 不足しているところは除きます。
- **使用されていない変数がないはずです。** - このことは、大量のバグを招く原因です。
- **セミコロンがないはずです。** - [It's] [1] [fine] [2] [Really！] [3]
- ** `（ '、' [`、or `` `` `のようにラインを起動しないでください。**
   - セミコロン省略時は必ず問題が生じる可能性があります。 - *自動的にチェックすることができるように用意されています。*
   - [More details] [4]
- **キーワードの後に​​スペースを使用します。** `if（condition）{...}`
- **関数名の後にスペースを使用します。** `function name（arg）{...}`
- 常に `==`の代わりに `===`を使用します。 - ただし、 `null || undefined`は `obj == null`で確認することができます。
- node.jsでerrパラメータは、常に処理する必要があります。
- 常にブラウザ全域に `window`プレフィックスを付けます。 - `document`と` navigator`は大丈夫です。
   - `open`、` length`、 `event`、` name`など不明なブラウザ全域を偶然使用することを防止します。
- ** [より多くの利点] [5]があります。** - * `standard`を試してみてください！*

[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons
[3]: https://www.youtube.com/watch?v=gsfbh17Ax9I
[4]: RULES.md#semicolons
[5]: RULES.md#javascript-standard-style

より良いアイデアを得るためには、JavaScript Standardスタイルで作成された[サンプルファイル]（https://github.com/expressjs/body-parser/blob/master/index.js）をご覧ください。または`standard`を使用している[何千ものプロジェクト]（https://raw.githubusercontent.com/standard/standard-packages/master/all.json）のいずれかを確認してください！

##目次

- クイックスタート
  - [インストール]（＃インストール）
  - [使い方]（＃使い方）
  - [理解していたら、次の手順を実行します]（＃理解 - うまくいけば - 次の - 実行します）
- 質疑応答
  - [なぜJavaScript Standard Styleを使用したいですか？]（＃なぜ-JavaScript-Standard-Styleを - 使用 - でしょうか）
  - [誰JavaScript Standard Styleを使うのですか？]（＃誰-JavaScript-Standard-Styleを - 使うのですか）
  - [テキスト編集プラグインはありますか？]（＃テキスト - 編集 - プラグインが - か）
  - [readmeに入れることができるバッジのロゴがありますか？]（＃readmeに - 入れ - こと - ある - バッジのロゴが - か）
  - [私はルールが一致しません。変更は可能ですか？]（＃私は - ルールが - 適合 - ん - 変更 - 可能ですか）
  - [しかし、このことは、実際のWeb標準はありません！]（＃しかし - この - は - 実際 - Web標準が - はありません）
  - [自動的にフォーマットを合わせてくれるのがありますか？]（＃自動的に - フォーマットを - 合わせる - が - か）
  - [どのようにすれば、ファイルを無視することができますか？]（＃どうすれば - ファイルを - 無視 - 数 - か）
  - [どのようにすると、警告を非表示にすることができますか？]（＃どうすれば - 警告を - 非表示 - 数 - か）
  - [全体namespaceを汚染させるライブラリを使用します。 「vaiable is not defined "エラーを回避するには、どうすればいいですか？]（＃全域-namespaceを - 汚染させる - ライブラリを - 使用し-vaiable-is-not-defined-エラーを - 防ぐために - どのように - する必要が - か）
  - [実験用JavaScript（ES Next）機能は、どのように使用か？]（＃実験-javascript-es-next-機能は - どのように - 使うのですか）
  - [javaScrptと他のFlowまたはtypescriptでも使用することができますか？]（＃javaScrptと - 他の-Flow-または-typescriptも - 使用 - することができ - ますか）
  - [Mocha、Jasmine、QUnitなどはいかがでしょうか？]（＃mocha-jasmine-qunit-などは - いかがでしょうか）
  - [Web Workesはいかがですか？]（＃web-workesは - いかがでしょうか）
  - [MarkdownまたはHTMLファイル内のコードを確認することができますか？]（＃markdown-または-html-ファイル - 内部の - コードを - 確認 - 数 - か）
  - [Git`pre-commit` hookはありますか？]（＃git-pre-commit-hookが - か）
  - [出力の両方を、華やかできれいに作成するにはどうすればいいですか？]（＃出力を - すべて - カラフルで - きれい - 作成するには - どのように - する必要が - か）
  - [Node.js APIはありますか？]（＃nodejs-apiが - か）
  - [`standard`貢献はどうすればいい？]（＃standard-貢献は - どのように - か）
- [ライセンス]（＃ライセンス）

##インストール

JavaScript Standard Styleを使用する最も簡単な方法は、Nodeコマンドプログラムを介してグローバルにインストールすることです。ターミナルで次のコマンドを実行します。

```bash
$ npm install standard--global
```

または`standard`をローカルにインストールして、単一のプロジェクトで使用することができます。

```bash
$ npm install standard--save-dev
```

*メモ：上記のコマンドを実行するには、[Node.js]（http://nodejs.org）と[npm]（https://npmjs.com）がインストールされている必要があります。*

##使い方

`standard`をインストールした後、` standard`プログラムを使用することができます。最も簡単な使用例は、現在の作業ディレクトリにあるすべてのJavaScriptファイルのスタイルを確認することです。

```bash
$ standard
Error：Use JavaScript Standard Style
  lib/ torrent.js：950：11：Expected「===」and instead saw」=='。
```

You can optionally pass in a directory（or directories）using the glob pattern。Be
sure to quote paths containing glob patterns so that they are expanded by
`standard` instead of your shell：
globパターンを使用してディレクトリ（またはディレクトリの）を選択的に渡すことができます。globパターンを含むパスを引用符で囲んでシェルの代わりに`standard`によって拡張されるようにすることができます。

```bash
$ standard"src/ util/**/*。js""test/**/*。js"
```

**メモ**基本的に`standard`は`**/*。js`、`**/*。jsx`パターンと一致するすべてのファイルを検索しています。

##理解していたら、次の手順を実行します

1.`package.json`に次のコードを追加します。

  ```json
  {
    "name"："my-cool-package"、
    「devDependencies"：{
      "standard"："*"
    }、
    "scripts"：{
      "test"："standard&& node my-tests.js"
    }
  }
  ```

2.`npm test`を実行するときに自動的にスタイルをチェックします。

  ```bash
  $ npm test
  Error：Use JavaScript Standard Style
    lib/ torrent.js：950：11：Expected「===」and instead saw」=='。
  ```

3. style意見のに対して、絶対フルリクエストを要求しないでください。

##なぜJavaScript Standard Styleを使用したいですか？

JavaScript Standard Styleの利点は、簡単であることです。誰も作業しているすべてのモジュール/プロジェクトの数百行styleの設定ファイルを維持しようとしません。もはや愚かな真似はやめて下さい。

このモジュールは、三つの方法で（または周辺の人々）の時間を節約することができます。

- **環境設定が必要ありません。**プロジェクトで一貫性のあるスタイルを適用するための最も簡単な方法です。ただ入れるだけです。
- **自動的にコードフォーマットを合わせています。** `standard --fix`を実行すると、汚れたり、一貫性のないコードとの別れすることができます。
- **スタイル問題とプログラマのエラーを早期に把握することができます。**レビューと貢献の間の関係を削除することにより、貴重なコードレビュー時間を節約することができます。

`standard`スタイルを採用するということは、個人的なスタイルよりもコード明快とコミュニティコラボレーションの重要性を優先とすることを意味します。これは、プロジェクト開発の文化に100％妥当でないかもしれないが、オープンソースは、初心者に敵対的な場所になることがあります。明確で自動化された貢献を期待するほどのプロジェクトがより健康的になります。

##人のJavaScript Standard Styleを使うのですか？

周辺には多くの人々！

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

会社以外の多くのコミュニティのメンバーは、ここに記載さには、[あまりにも多くの]（https://raw.githubusercontent.com/standard/standard-packages/master/all.json）パッケージが`standard`を使用します。

また、GitHubの[Clean Code Linter]（https://github.com/showcases/clean-code-linters）ショーケースでも見ることができます。

##テキスト編集プラグインはありますか？

まず、`standard`をインストールします。その後、エディタに適切なプラグインをインストールしてください。

### Sublime Text

**[Package Control][sublime-1]**を使用して、**[SublimeLinter][sublime-2]**と**[SublimeLinter-contrib-standard][sublime-3]**をインストールします。

保存時に自動的にフォーマットを適用するには、**[StandardFormat][sublime-4]**をインストールしてください。

[sublime-1]：https://packagecontrol.io/
[sublime-2]：http://www.sublimelinter.com/en/latest/
[sublime-3]：https://packagecontrol.io/packages/SublimeLinter-contrib-standard
[sublime-4]：https://packagecontrol.io/packages/StandardFormat

### Atom

** [linter-js-standard] [atom-1] **をインストールします。

または** [linter-js-standard-engine] [atom-4] **をインストールすることができます。 `standard`バージョンをバンドルする代わりに、現在のプロジェクトにインストールされてバージョンを自動的に使用します。また、** [standard-engine] [atom-5] **をベースにした他のlinterで動作します。

保存時に自動的にフォーマットを適用するには、** [standard-formatter] [atom-2] **をインストールします。スニペットの場合** [standardjs-snippets] [atom-3] **をインストールします。

[atom-1]：https://atom.io/packages/linter-js-standard
[atom-2]：https://atom.io/packages/standard-formatter
[atom-3]：https://atom.io/packages/standardjs-snippets
[atom-4]：https://atom.io/packages/linter-js-standard-engine
[atom-5]：https://github.com/Flet/standard-engine

### Visual Studio Code

** [vscode-standardjs] [vscode-1] **をインストールします。 （自動フォーマットをサポートします。）

JSスニペットの場合** [vscode-standardjs-snippets] [vscode-2] **をインストールします。 Reactスニペットの場合** [vscode-react-standard] [vscode-3] **をインストールします。

[vscode-1]：https://marketplace.visualstudio.com/items/chenxsan.vscode-standardjs
[vscode-2]：https://marketplace.visualstudio.com/items?itemName=capaj.vscode-standardjs-snippets
[vscode-3]：https://marketplace.visualstudio.com/items/TimonVS.ReactSnippetsStandard

### Vim

**[ale][vim-1]**をインストールします。

For automatic formatting on save、add these lines to`.vimrc`：

保存時に自動的にフォーマットを適用するには、コードを`.vimrc`に追加します。

```vim
autocmd bufwritepost*.js silent！standard--fix％
set autoread
```

考慮すべき代替プラグインでは、[neomake][vim-2]と[syntastic][vim-3]があり、両方の標準のサポートが組み込まれています。（さらに設定が必要になる場合があります）

[vim-1]：https://github.com/w0rp/ale
[vim-2]：https://github.com/neomake/neomake
[vim-3]：https://github.com/vim-syntastic/syntastic

### Emacs

**[Flycheck][emacs-1]**をインストールして、**[manual][emacs-2]**を確認して、プロジェクトで有効にする方法を確認してください。

[emacs-1]：http://www.flycheck.org
[emacs-2]：http://www.flycheck.org/en/latest/user/installation.html

### Brackets

extension registryで**["Standard Code Style"][brackets-1]**を検索して「Install」をクリックします。

[brackets-1]：https://github.com/ishamf/brackets-standard/

### WebStorm（PhpStorm、IntelliJ、RubyMine、JetBrains、etc.）

WebStromは`standard`が直接IDEで使用可能と[基本的なサポートに関する最近の発表]（https://blog.jetbrains.com/webstorm/2017/01/webstorm-2017-1-eap-171-2272/）しました。

もし、手動で`standard`を構成するには、[ガイド]（[webstorm-1]）を実行します。これPhpStorm、IntelliJ、RubyMineなど、すべてのJetBrains製品に適用されます。

[webstorm-1]：docs/ webstorm.md

## readmeに入れることができるバッジのロゴがありますか？

はい！プロジェクトで`standard`を使用する場合、readmeにはバッジのいずれかを含めて、コードがstandardスタイルを使用していることを人々に知らせることができます。

[![JavaScript Style Guide](https://cdn.rawgit.com/standard/standard/master/badge.svg)](https://github.com/standard/standard)

```md
[![JavaScript Style Guide](https://cdn.rawgit.com/standard/standard/master/badge.svg)](https://github.com/standard/standard)
```

[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

```md
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
```

##私は、ルールが一致しません。変更は可能ですか？

なりません。 `standard`の全体的なポイントは、コードスタイルの[bikeshedding] [bikeshedding]を避けることによって、時間を節約することです。タブとスペースなどについては、オンラインで多くの議論があるので、解決されないでしょう。これらの議論は、何も得られないようにします。最終的には `何かを選ばなければなら`です。それは `standard`の哲学です。これは `だけ何かを選択してください 'という意見です。うまくいけば、ユーザーが自分の意見を守ることについての価値を見ることを願って。

何百ものESLintルールを個別に構成する場合 `eslint`を直接[eslint-config-standard]（https://github.com/standard/eslint-config-standard）と一緒に使用して変更を一番上に配置することがすることができます。
[ `standard-eject`]（https://github.com/josephfrazier/standard-eject）は` standard`で `eslint`と` eslint-config-standard`への移行を支援することができます。

ヒント：標準を使用して続行します。あなたの時間を消費している実用的な問題を解決してください！ ：P

[bikeshedding]：https://www.freebsd.org/doc/en/books/faq/misc.html#bikeshed-painting

##しかし、このことは、実際のWeb標準はありません！

もちろん、標準ではありません！ここで提示されたスタイルは、公式Web標準のグループと関連がないので、 `ECMA / standard`ではなく、` standard / standard`という理由です。

「standard」という言葉は、「web standard "以上の意味を持っています:-)

例えば、
- このモジュールは、私たちのコードを高レベルの品質を維持するのに役立ちます。
- このモジュールは、新しい貢献者がいくつかの基本的なスタイルの標準に準拠するようにします。

##自動的にフォーマットを合わせてくれることがありますか？

はい！ほとんどの問題を自動的に修正するには、 `standard --fix`を使用することができます。

`standard --fix`は最大の便宜のために` standard`に内蔵されています。ほとんどの問題は修正できますが、いくつかのエラー（エラー処理を忘れてしまうこと）は、手動で解決する必要があります。

時間を節約するために `standard`は自動的に変更できる問題を発見すると、「` Run standard --fix to automatically fix some problems`」メッセージを出力します。

##どうすればファイルを無視することができますか？

特定のパス（`node_modules/'、' coverage/`、`vendor/`、`*.min.js`、` bundle.js`、`.git/`のように``で始まるファイル/フォルダ）は自動的に無視されます。

プロジェクトのルート`.gitignore`ファイルのパスが自動的に無視されます。

時には追加フォルダまたは特定の縮小ファイルを無視する必要があります。これを行うには、`package.json`に` standard.ignore`属性を追加します。

```json
"standard"：{
  "ignore"：[
    "**/ out/"、
    "/ lib/ select2/"、
    "/ lib/ ckeditor/"、
    "tmp.js"
  ]
}
```

##どのようにすると、警告を非表示にすることができますか？

まれに、規則に違反して `standard`によって生成された警告を非表示にする必要があります。

JavaScriptの標準スタイルは、[ESLint]（http://eslint.org/）を使用し、ESLintを直接使用した場合、一般的に、警告を非表示にすることができます。

詳細な出力を得るために（無視特定のルールの名前を見つけることができるように）、以下を実行します。

`` `bash
$ standard --verbose
Error：Use JavaScript Standard Style
  routes / error.js：20：36：「file」was used before it was defined。 （no-use-before-define）
`` `

特定の行で**すべてのルール**を無効にすることができます。

`` `js
file = 'I know what I am doing' // eslint-disable-line
`` `

あるいは、特定の行で** `" no-use-before-define "`ルールのみ**無効にすることができます。

`` `js
file = 'I know what I am doing' // eslint-disable-line no-use-before-define
`` `

`" no-use-before-define "`ルールを複数行に適用することができます。

`` `js
/ * eslint-disable no-use-before-define * /
console.log（ 'offending code goes here ...」）
console.log（ 'offending code goes here ...」）
console.log（ 'offending code goes here ...」）
/ * eslint-enable no-use-before-define * /
`` `

##全域namespaceを汚染させるライブラリを使用します。「vaiable is not defined"エラーを回避するには、どうすればいいですか？

いくつかのパッケージ（例えば、`mocha`）は、グローバルオブジェクト（悪い形！）に機能（例えば、` describe`、`it`）を指定します。この関数は、定義されていないか、コードのどこでも必要とされることがありますので、 `standard`で定義されていない変数を使用していると警告して（一般的には、このルールは、タイプミスをキャッチするために役立ちます）。しかし、私たちは、このグローバル変数について、これを無効にしようとします。

`standard`（コードを読んでいる人だけでなく、）で特定の変数がコード内でグローバルであることがわかるように、ファイルの先頭に追加してください。

```js
/* global myVar1、myVar2*/
```

数百個のファイルがある場合は、すべてのファイルにコメントを追加していないことをお勧め。この場合は、次を実行します。

```bash
$ standard--global myVar1--global myVar2
```

あるいは`package.json`に次のコードを追加します。

```json
{
  "standard"：{
    "globals"：["myVar1"、"myVar2"]
  }
}
```

*ノート：`global`と` globals`は同じです。

##実験用JavaScript（ES Next）機能は、どのように使用か？

`standard`は提案プロセスの「ステップ4」の言語機能の提案を含む、最新のECMAScript機能ES8（ES2017）をサポートします。

実験用の言語機能をサポートするために、`standard`は、カスタムJavaScriptパーサを指定することをサポートします。カスタムパーサーを使用する前に、追加された複雑さが価値があることを考慮してください。

カスタムパーサーを使用する前に、npmモジュールをインストールします。

```bash
npm install babel-eslint--save-dev
```

次の手順を実行します。

```bash
$ standard--parser babel-eslint
```

あるいは、`package.json`に次のコードを追加します。

```json
{
  "standard"：{
    "parser"："babel-eslint"
  }
}
```

`standard」は、グローバルにインストールされると（つまり、` npm install standard--global`）、`babel-eslint`を` npm install babel-eslint--global`と一緒にインストールしてください。

## javaScrptと他のFlowまたはtypescriptでも使用することができますか？

`standard`は、最新のECMAScriptの機能をサポートします。しかし、FlowとTypeScriptは新しい構文を言語に追加する必要があるため、すぐに使用することができません。

JavaScript言語のバリエーションをサポートするために、 `standard`は変更された構文を処理することができるESLintプラグインだけでなく、カスタムJavaScriptパーサを指定することをサポートします。 JavaScript言語のバリエーションを使用する前に追加された複雑さの価値があることを考慮してください。

### Flow

Flowを使用するには、 `babel-eslint`をパーサとして使用して` eslint-plugin-flowtype`をプラグインとして使用して `standard`を実行する必要があります。

`` `bash
npm install babel-eslint eslint-plugin-flowtype --save-dev
`` `

以下を実行します。

`` `bash
$ standard --parser babel-eslint --plugin flowtype
`` `

または、 `package.json`に次のコードを追加します。

`` `json
{
  "standard"：{
    "parser"： "babel-eslint"、
    "plugins"：[ "flowtype"]
  }
}
`` `

*注意： `plugin`と` plugins`は同じです。*

もし `standard`がグローバルにインストールすると、（つまり、` npm install standard - global`）、 `babel-eslint`と` eslint-plugin-flowtype`も一緒にインストールする必要があります。 `npm install babel-eslint eslint-plugin-flowtype --global`。

### TypeScript

TypeScriptを使用するには、 `typescript-eslint-parser`をパーサに` standard`を、プラグインに `eslint-plugin-typescript`を実行して、標準lint` * .ts`ファイルに送信します。 （デフォルトではないから）

`` `bash
npm install typescript-eslint-parser eslint-plugin-typescript --save-dev
`` `

以下を実行します。


`` `bash
$ standard --parser typescript-eslint-parser --plugin typescript * .ts
`` `

または、 `package.json`に次のコードを追加します。

`` `json
{
  "standard"：{
    "parser"： "typescript-eslint-parser"、
    "plugins"：[ "typescript"]
  }
}
`` `

`package.json`を使用すると、以下のように実行することができます。

`` `bash
standard * .ts
`` `

`standard`グローバルにインストールされている場合（つまり、` npm install standard --global`） `npm install typescript-eslint-parser eslint-plugin-typescript --global`を使用して` eslint-plugin-flowtype`と `typescript -eslint-parser`をグローバルにインストールする必要があります。

## Mocha、Jasmine、QUnitなどはいかがでしょうか？

テストファイルでmochaをサポートするには、テストファイルの先頭に以下を追加します。

`` `js
/ * eslint-env mocha * /
`` `

あるいは、以下を実行します。

`` `bash
$ standard --env mocha
`` `

`mocha`は` jasmine`、 `qunit`、` phantomjs`のいずれかになることがあります。全リストを表示するにはESLintの[specifying environments（仕様書）]（http://eslint.org/docs/user-guide/configuring.html#specifying-environments）を確認してください。このような環境で使用できるグローバルのリストを表示するには、[globals]（https://github.com/sindresorhus/globals/blob/master/globals.json）npmモジュールを確認してください。

**注： `env`と` envs`は同じです。**

## Web Workesはいかがでしょうか？

適用しようとするファイルの先頭に次のコメントコードを追加します。

`` `js
/ * eslint-env serviceworker * /
`` `

これは `standard`（コードを読んでいる人だけでなく、）がweb workerコードで`自分 `グローバル（global）であることを知ることができようになります。

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
