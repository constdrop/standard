# JavaScript Standard Style

<p align="center">
  <a href="/docs/RULES-en.md">English</a> •
  <a href="/docs/RULES-esla.md">Español (Latinoamérica)</a> •
  <a href="/docs/RULES-fr.md">Français</a> •
  <a href="/docs/RULES-iteu.md">Italiano (Italian)</a> •
  <a href="/docs/RULES-jajp.md">日本語 (Japanese)</a> •
  <a href="/docs/RULES-kokr.md">한국어 (Korean)</a> •
  <a href="/docs/RULES-ptbr.md">Português (Brasil)</a> •
  <a href="/docs/RULES-zhcn.md">简体中文 (Simplified Chinese)</a> •
  <a href="/docs/RULES-zhtw.md">繁體中文 (Taiwanese Mandarin)</a>
</p>

[![js-standard-style](https://cdn.rawgit.com/standard/standard/master/badge.svg)](https://github.com/standard/standard)

これは[standard](https://github.com/standard/standard)のJavaScriptのルールをまとめたものです。

`standard`について学ぶ最良の方法は、インストールしてあなたのコードで試してみることです。

## ルール

* インデントには **2つのスペース** を使用します。

  eslint: [`indent`](http://eslint.org/docs/rules/indent)

  ```js
  function hello (name) {
    console.log('hi', name)
  }
  ```

* エスケープを避けるために **文字列にはシングルクォーテーション** を使用します。

  eslint: [`quotes`](http://eslint.org/docs/rules/quotes)

  ```js
  console.log('hello there')
  $("<div class='box'>")
  ```

* **使用しない変数を定義しません。**

  eslint: [`no-unused-vars`](http://eslint.org/docs/rules/no-unused-vars)

  ```js
  function myFunction () {
    var result = something()   // ✗ 悪い例
  }
  ```

* **予約語の後にスペースを入れます。**

  eslint: [`keyword-spacing`](http://eslint.org/docs/rules/keyword-spacing)

  ```js
  if (condition) { ... }   // ✓ 良い例
  if(condition) { ... }    // ✗ 悪い例
  ```

* **関数の宣言の括弧の前にスペースを入れます。**

  eslint: [`space-before-function-paren`](http://eslint.org/docs/rules/space-before-function-paren)

  ```js
  function name (arg) { ... }   // ✓ 良い例
  function name(arg) { ... }    // ✗ 悪い例

  run(function () { ... })      // ✓ 良い例
  run(function() { ... })       // ✗ 悪い例
  ```

* `==` ではなく `===` を **常に使用** します。<br>
  例外： `null || undefined` は `obj == null` で評価しても構いません。

  eslint: [`eqeqeq`](http://eslint.org/docs/rules/eqeqeq)

  ```js
  if (name === 'John')   // ✓ 良い例
  if (name == 'John')    // ✗ 悪い例
  ```

  ```js
  if (name !== 'John')   // ✓ 良い例
  if (name != 'John')    // ✗ 悪い例
  ```

* **中置記法演算子の前後** にスペースを入れます。

  eslint: [`space-infix-ops`](http://eslint.org/docs/rules/space-infix-ops)

  ```js
  // ✓ 良い例
  var x = 2
  var message = 'hello, ' + name + '!'
  ```

  ```js
  // ✗ 悪い例
  var x=2
  var message = 'hello, '+name+'!'
  ```

* **カンマの後にスペースを入れます。**

  eslint: [`comma-spacing`](http://eslint.org/docs/rules/comma-spacing)

  ```js
  // ✓ 良い例
  var list = [1, 2, 3, 4]
  function greet (name, options) { ... }
  ```

  ```js
  // ✗ 悪い例
  var list = [1,2,3,4]
  function greet (name,options) { ... }
  ```

* **elseステートメント** は波括弧と同じ行に置きます。

  eslint: [`brace-style`](http://eslint.org/docs/rules/brace-style)

  ```js
  // ✓ 良い例
  if (condition) {
    // ...
  } else {
    // ...
  }
  ```

  ```js
  // ✗ 悪い例
  if (condition) {
    // ...
  }
  else {
    // ...
  }
  ```

* **複数行のifステートメント** には波括弧を使用します。

  eslint: [`curly`](http://eslint.org/docs/rules/curly)

  ```js
  // ✓ 良い例
  if (options.quiet !== true) console.log('done')
  ```

  ```js
  // ✓ 良い例
  if (options.quiet !== true) {
    console.log('done')
  }
  ```

  ```js
  // ✗ 悪い例
  if (options.quiet !== true)
    console.log('done')
  ```

* `err` 引数がある場合は **常に処理します。**

  eslint: [`handle-callback-err`](http://eslint.org/docs/rules/handle-callback-err)
  ```js
  // ✓ 良い例
  run(function (err) {
    if (err) throw err
    window.alert('done')
  })
  ```

  ```js
  // ✗ 悪い例
  run(function (err) {
    window.alert('done')
  })
  ```

  * **ブラウザグローバルを宣言する** 場合には、 `/* global */` コメントを付加します。<br>
    例外: `window`, `document`, `navigator`<br>
    `open`, `length`, `event`, `name`のような漠然とした名前を、ブラウザグローバルで偶発的に使用することを防ぎます

    ```js
    /* global alert, prompt */

    alert('hi')
    prompt('ok?')
    ```

    明示的に`window`を記述することで、その関数やプロパティを参照することはできますが、`window`の代わりに`self`を使うワーカーでは動作しません。

    eslint: [`no-undef`](http://eslint.org/docs/rules/no-undef)

    ```js
    window.alert('hi')   // ✓ 良い例
    ```

* **複数行の空白行は避けます。**

  eslint：[ `no-multiple-empty-lines`]（http://eslint.org/docs/rules/no-multiple-empty-lines）

  eslint: [`no-multiple-empty-lines`](http://eslint.org/docs/rules/no-multiple-empty-lines)

  ```js
  // ✓ 良い例
  var value = 'hello world'
  console.log(value)
  ```

  ```js
  // ✗ 悪い例
  var value = 'hello world'


  console.log(value)
  ```

* 複数行の **三項演算子** を使用する場合は、`?`と`:`をそれぞれの行の先頭に置きます。

  eslint: [`operator-linebreak`](http://eslint.org/docs/rules/operator-linebreak)

  ```js
  // ✓ 良い例
  var location = env.development ? 'localhost' : 'www.api.com'

  // ✓ 良い例
  var location = env.development
    ? 'localhost'
    : 'www.api.com'

  // ✗ 悪い例
  var location = env.development ?
    'localhost' :
    'www.api.com'
  ```

* **varによる宣言** では、宣言ごとにvarステートメントを書きます。

  eslint: [`one-var`](http://eslint.org/docs/rules/one-var)

  ```js
  // ✓ 良い例
  var silent = true
  var verbose = true

  // ✗ 悪い例
  var silent = true, verbose = true

  // ✗ 悪い例
  var silent = true,
      verbose = true
  ```

* **代入を含んだ条件** はさらに括弧で囲みます。これは式が等号(`===`)のミスではなく、意図的に代入(`=`)であることを明示するものです。

  eslint: [`no-cond-assign`](http://eslint.org/docs/rules/no-cond-assign)

  ```js
  // ✓ 良い例
  while ((m = text.match(expr))) {
    // ...
  }

  // ✗ 悪い例
  while (m = text.match(expr)) {
    // ...
  }
  ```

* **1行のブロックでは波括弧の内側にスペースを入れます。**

  eslint: [`block-spacing`](http://eslint.org/docs/rules/block-spacing)

  ```js
    function foo () {return true}    // ✗ 悪い例
    function foo () { return true }  // ✓ 良い例
  ```

* **変数や関数名にはキャメルケース（camelcase）を使用します。**

  eslint: [`camelcase`](http://eslint.org/docs/rules/camelcase)

  ```js
    function my_function () { }    // ✗ 悪い例
    function myFunction () { }     // ✓ 良い例

    var my_var = 'hello'           // ✗ 悪い例
    var myVar = 'hello'            // ✓ 良い例
  ```

* **最後に付随するカンマは避けます。**

  eslint: [`comma-dangle`](http://eslint.org/docs/rules/comma-dangle)

  ```js
    var obj = {
      message: 'hello',   // ✗ 悪い例
    }
  ```

* **カンマは行末に配置します。**

  eslint: [`comma-style`](http://eslint.org/docs/rules/comma-style)

  ```js
    var obj = {
      foo: 'foo'
      ,bar: 'bar'   // ✗ 悪い例
    }

    var obj = {
      foo: 'foo',
      bar: 'bar'   // ✓ 良い例
    }
  ```

* **ドットはプロパティと同じ行に配置します。**

  eslint: [`dot-location`](http://eslint.org/docs/rules/dot-location)

  ```js
    console.
      log('hello')  // ✗ 悪い例

    console
      .log('hello') // ✓ 良い例
  ```

* **ファイルは空行で終わらなくてはなりません。**

  eslint: [`eol-last`](http://eslint.org/docs/rules/eol-last)

* **関数の識別子と呼び出しの間にはスペースを入れません。**

  eslint: [`func-call-spacing`](http://eslint.org/docs/rules/func-call-spacing)

  ```js
  console.log ('hello') // ✗ 悪い例
  console.log('hello')  // ✓ 良い例
  ```

* **キーと値のペアのコロンと値の間にスペースを入れます。**

  eslint: [`key-spacing`](http://eslint.org/docs/rules/key-spacing)

  ```js
  var obj = { 'key' : 'value' }    // ✗ 悪い例
  var obj = { 'key' :'value' }     // ✗ 悪い例
  var obj = { 'key':'value' }      // ✗ 悪い例
  var obj = { 'key': 'value' }     // ✓ 良い例
  ```

* **コンストラクターの名前は大文字で始めます。**

  eslint: [`new-cap`](http://eslint.org/docs/rules/new-cap)

  ```js
  function animal () {}
  var dog = new animal()    // ✗ 悪い例

  function Animal () {}
  var dog = new Animal()    // ✓ 良い例
  ```

* **引数のないコンストラクタは括弧をつけて呼び出さなければなりません。**

  eslint: [`new-parens`](http://eslint.org/docs/rules/new-parens)

  ```js
  function Animal () {}
  var dog = new Animal    // ✗ 悪い例
  var dog = new Animal()  // ✓ 良い例
  ```

* **オブジェクトにsetterを定義した場合、getterも含めなくてはなりません。**

  eslint: [`accessor-pairs`](http://eslint.org/docs/rules/accessor-pairs)

  ```js
  var person = {
    set name (value) {    // ✗ 悪い例
      this._name = value
    }
  }

  var person = {
    set name (value) {
      this._name = value
    },
    get name () {         // ✓ 良い例
      return this._name
    }
  }
  ```

* **派生クラスのコンストラクタは、`super`を呼び出さなくてはなりません。**

  eslint: [`constructor-super`](http://eslint.org/docs/rules/constructor-super)

  ```js
  class Dog {
    constructor () {
      super()   // ✗ 悪い例
    }
  }

  class Dog extends Mammal {
    constructor () {
      super()   // ✓ 良い例
    }
  }
  ```

* **配列コンストラクタではなく配列リテラルを使用します。**

  eslint: [`no-array-constructor`](http://eslint.org/docs/rules/no-array-constructor)

  ```js
  var nums = new Array(1, 2, 3)   // ✗ 悪い例
  var nums = [1, 2, 3]            // ✓ 良い例
  ```

* **`arguments.callee`と`arguments.caller`を使用してはいけません。**

  eslint: [`no-caller`](http://eslint.org/docs/rules/no-caller)

  ```js
  function foo (n) {
    if (n <= 0) return

    arguments.callee(n - 1)   // ✗ 悪い例
  }

  function foo (n) {
    if (n <= 0) return

    foo(n - 1)                // ✓ 良い例
  }
  ```

* **クラスで宣言された変数を変更してはいけません。**

  eslint: [`no-class-assign`](http://eslint.org/docs/rules/no-class-assign)

  ```js
  class Dog {}
  Dog = 'Fido'    // ✗ 悪い例
  ```

* **`const`を使用して宣言された変数を変更してはいけません。**

  eslint: [`no-const-assign`](http://eslint.org/docs/rules/no-const-assign)

  ```js
  const score = 100
  score = 125       // ✗ 悪い例
  ```

* **条件(繰り返しを除く)で固定した条件式を使用してはいけません。**

  eslint: [`no-constant-condition`](http://eslint.org/docs/rules/no-constant-condition)

  ```js
  if (false) {    // ✗ 悪い例
    // ...
  }

  if (x === 0) {  // ✓ 良い例
    // ...
  }

  while (true) {  // ✓ 良い例
    // ...
  }
  ```

* **正規表現に制御文字を含めてはいけません。**

  eslint: [`no-control-regex`](http://eslint.org/docs/rules/no-control-regex)

  ```js
  var pattern = /\x1f/    // ✗ 悪い例
  var pattern = /\x20/    // ✓ 良い例
  ```

* **`debugger`を使用してはいけません。**

  eslint: [`no-debugger`](http://eslint.org/docs/rules/no-debugger)

  ```js
  function sum (a, b) {
    debugger      // ✗ 悪い例
    return a + b
  }
  ```

* **変数に`delete`演算子を使用してはいけません。**

  eslint: [`no-delete-var`](http://eslint.org/docs/rules/no-delete-var)

  ```js
  var name
  delete name     // ✗ 悪い例
  ```

* **関数の定義の際、重複した引数を使用してはいけません。**

  eslint: [`no-dupe-args`](http://eslint.org/docs/rules/no-dupe-args)

  ```js
  function sum (a, b, a) {  // ✗ 悪い例
    // ...
  }

  function sum (a, b, c) {  // ✓ 良い例
    // ...
  }
  ```

* **クラスのメンバーに重複した名前を使用してはいけません。**

  eslint: [`no-dupe-class-members`](http://eslint.org/docs/rules/no-dupe-class-members)

  ```js
  class Dog {
    bark () {}
    bark () {}    // ✗ 悪い例
  }
  ```

* **オブジェクトリテラルに重複したキーを使用してはいけません。**

  eslint: [`no-dupe-keys`](http://eslint.org/docs/rules/no-dupe-keys)

  ```js
  var user = {
    name: 'Jane Doe',
    name: 'John Doe'    // ✗ 悪い例
  }
  ```

* **`switch`ステートメントで重複した`case`ラベルを使用してはいけません。**

  eslint: [`no-duplicate-case`](http://eslint.org/docs/rules/no-duplicate-case)

  ```js
  switch (id) {
    case 1:
      // ...
    case 1:     // ✗ 悪い例
  }
  ```

* **1つのモジュールにつき1つのimportステートメントを使用します。**

  eslint: [`no-duplicate-imports`](http://eslint.org/docs/rules/no-duplicate-imports)

  ```js
  import { myFunc1 } from 'module'
  import { myFunc2 } from 'module'          // ✗ 悪い例

  import { myFunc1, myFunc2 } from 'module' // ✓ 良い例
  ```

* **正規表現で空の文字クラスを含めてはいけません。**

  eslint: [`no-empty-character-class`](http://eslint.org/docs/rules/no-empty-character-class)

  ```js
  const myRegex = /^abc[]/      // ✗ 悪い例
  const myRegex = /^abc[a-z]/   // ✓ 良い例
  ```

* **空のdestructuringパターン(分割代入)を使用してはいけません。**

  eslint: [`no-empty-pattern`](http://eslint.org/docs/rules/no-empty-pattern)

  ```js
  const { a: {} } = foo         // ✗ 悪い例
  const { a: { b } } = foo      // ✓ 良い例
  ```

* **`eval()`を使用してはいけません。**

  eslint: [`no-eval`](http://eslint.org/docs/rules/no-eval)

  ```js
  eval( "var result = user." + propName ) // ✗ 悪い例
  var result = user[propName]             // ✓ 良い例
  ```

* **`catch`節の例外に再代入をしてはいけません。**

  eslint: [`no-ex-assign`](http://eslint.org/docs/rules/no-ex-assign)

  ```js
  try {
    // ...
  } catch (e) {
    e = 'new value'             // ✗ 悪い例
  }

  try {
    // ...
  } catch (e) {
    const newVal = 'new value'  // ✓ 良い例
  }
  ```

* **ネイティブオブジェクトを拡張してはいけません。**

  eslint: [`no-extend-native`](http://eslint.org/docs/rules/no-extend-native)

  ```js
  Object.prototype.age = 21     // ✗ 悪い例
  ```

* **不要な関数のバインドは避けます。**

  eslint: [`no-extra-bind`](http://eslint.org/docs/rules/no-extra-bind)

  ```js
  const name = function () {
    getName()
  }.bind(user)    // ✗ 悪い例

  const name = function () {
    this.getName()
  }.bind(user)    // ✓ 良い例
  ```

* **不要なbooleanキャストは避けます。**

  eslint: [`no-extra-boolean-cast`](http://eslint.org/docs/rules/no-extra-boolean-cast)

  ```js
  const result = true
  if (!!result) {   // ✗ 悪い例
    // ...
  }

  const result = true
  if (result) {     // ✓ 良い例
    // ...
  }
  ```

* **関数式の周りに不要な括弧をつけません。**

  eslint: [`no-extra-parens`](http://eslint.org/docs/rules/no-extra-parens)

  ```js
  const myFunc = (function () { })   // ✗ 悪い例
  const myFunc = function () { }     // ✓ 良い例
  ```

* **`switch`の複数ケースの通過を避けるために`break`を使用します。**

  eslint: [`no-fallthrough`](http://eslint.org/docs/rules/no-fallthrough)

  ```js
  switch (filter) {
    case 1:
      doSomething()    // ✗ 悪い例
    case 2:
      doSomethingElse()
  }

  switch (filter) {
    case 1:
      doSomething()
      break           // ✓ 良い例
    case 2:
      doSomethingElse()
  }

  switch (filter) {
    case 1:
      doSomething()
      // fallthrough  // ✓ 良い例
    case 2:
      doSomethingElse()
  }
  ```

* **数字に挟まれない小数点を使用しません。**

  eslint: [`no-floating-decimal`](http://eslint.org/docs/rules/no-floating-decimal)

  ```js
  const discount = .5      // ✗ 悪い例
  const discount = 0.5     // ✓ 良い例
  ```

* **宣言された関数に再代入してはいけません。**

  eslint: [`no-func-assign`](http://eslint.org/docs/rules/no-func-assign)

  ```js
  function myFunc () { }
  myFunc = myOtherFunc    // ✗ 悪い例
  ```

* **読み取り専用のグローバル変数に再代入してはいけません。**

  eslint: [`no-global-assign`](http://eslint.org/docs/rules/no-global-assign)

  ```js
  window = {}     // ✗ 悪い例
  ```

* **暗黙の`eval()`が含まれないようにします。**

  eslint: [`no-implied-eval`](http://eslint.org/docs/rules/no-implied-eval)

  ```js
  setTimeout("alert('Hello world')")                   // ✗ 悪い例
  setTimeout(function () { alert('Hello world') })     // ✓ 良い例
  ```

* **ネストされたブロックの中で関数を宣言してはいけません。**

  eslint: [`no-inner-declarations`](http://eslint.org/docs/rules/no-inner-declarations)

  ```js
  if (authenticated) {
    function setAuthUser () {}    // ✗ 悪い例
  }
  ```

* **`RegExp`コンストラクタに誤った正規表現文字列を含めてはいけません。**

  eslint: [`no-invalid-regexp`](http://eslint.org/docs/rules/no-invalid-regexp)

  ```js
  RegExp('[a-z')    // ✗ 悪い例
  RegExp('[a-z]')   // ✓ 良い例
  ```

* **不規則なスペースを入れません。**

  eslint: [`no-irregular-whitespace`](http://eslint.org/docs/rules/no-irregular-whitespace)

  ```js
  function myFunc () /*<NBSP>*/{}   // ✗ 悪い例
  ```

* **`__iterator__`は使用しません。**

  eslint: [`no-iterator`](http://eslint.org/docs/rules/no-iterator)

  ```js
  Foo.prototype.__iterator__ = function () {}   // ✗ 悪い例
  ```

* **スコープ内変数と共通の名前のラベルを使ってはいけません。**

  eslint: [`no-label-var`](http://eslint.org/docs/rules/no-label-var)

  ```js
  var score = 100
  function game () {
    score: while (true) {      // ✗ 悪い例
      score -= 10
      if (score > 0) continue score
      break
    }
  }
  ```

* **ラベルステートメントを使用してはいけません。**

  eslint: [`no-labels`](http://eslint.org/docs/rules/no-labels)

  ```js
  label:
    while (true) {
      break label     // ✗ 悪い例
    }
  ```

* **ブロックの不要なネストをしません。**

  eslint: [`no-lone-blocks`](http://eslint.org/docs/rules/no-lone-blocks)

  ```js
  function myFunc () {
    {                   // ✗ 悪い例
      myOtherFunc()
    }
  }

  function myFunc () {
    myOtherFunc()       // ✓ 良い例
  }
  ```

* **インデントにスペースとタブを混ぜて使用しません。**

  eslint: [`no-mixed-spaces-and-tabs`](http://eslint.org/docs/rules/no-mixed-spaces-and-tabs)

* **インデント以外に複数のスペースを使用しません。**

  eslint: [`no-multi-spaces`](http://eslint.org/docs/rules/no-multi-spaces)

  ```js
  const id =    1234    // ✗ 悪い例
  const id = 1234       // ✓ 良い例
  ```

* **マルチライン文字列は使用しません。**

  eslint: [`no-multi-str`](http://eslint.org/docs/rules/no-multi-str)

  ```js
  const message = 'Hello \
                   world'     // ✗ 悪い例
  ```

* **オブジェクトを変数に代入しない`new`は行いません。**

  eslint: [`no-new`](http://eslint.org/docs/rules/no-new)

  ```js
  new Character()                     // ✗ 悪い例
  const character = new Character()   // ✓ 良い例
  ```

* **`Function`コンストラクタは使用しません。**

  eslint: [`no-new-func`](http://eslint.org/docs/rules/no-new-func)

  ```js
  var sum = new Function('a', 'b', 'return a + b')    // ✗ 悪い例
  ```

* **`Object`コンストラクタは使用しません。**

  eslint: [`no-new-object`](http://eslint.org/docs/rules/no-new-object)

  ```js
  let config = new Object()   // ✗ 悪い例
  ```

* **`new require`は使用しません。**

  eslint: [`no-new-require`](http://eslint.org/docs/rules/no-new-require)

  ```js
  const myModule = new require('my-module')    // ✗ 悪い例
  ```

* **`Symbol`コンストラクタは使用しません。**

  eslint: [`no-new-symbol`](http://eslint.org/docs/rules/no-new-symbol)

  ```js
  const foo = new Symbol('foo')   // ✗ 悪い例
  ```

* **プリミティブラッパーのインスタンスは使用しません。**

  eslint: [`no-new-wrappers`](http://eslint.org/docs/rules/no-new-wrappers)

  ```js
  const message = new String('hello')   // ✗ 悪い例
  ```

* **グローバルオブジェクトのプロパティを関数として呼んではいけません。**

  eslint: [`no-obj-calls`](http://eslint.org/docs/rules/no-obj-calls)

  ```js
  const math = Math()   // ✗ 悪い例
  ```

* **8進数リテラルを使用してはいけません。**

  eslint: [`no-octal`](http://eslint.org/docs/rules/no-octal)

  ```js
  const num = 042     // ✗ 悪い例
  const num = '042'   // ✓ 良い例
  ```

* **文字列リテラルには、8進数のエスケープシーケンスを使用してはいけません。**

  eslint: [`no-octal-escape`](http://eslint.org/docs/rules/no-octal-escape)

  ```js
  const copyright = 'Copyright \251'  // ✗ 悪い例
  ```

* **`__dirname`と` __filename`を使用するときは文字列の連結は避けます。**

  eslint: [`no-path-concat`](http://eslint.org/docs/rules/no-path-concat)

  ```js
  const pathToFile = __dirname + '/app.js'            // ✗ 悪い例
  const pathToFile = path.join(__dirname, 'app.js')   // ✓ 良い例
  ```

* **`__proto__`を使用してはいけません。** 代わりに`getPrototypeOf`を使用します。

  eslint: [`no-proto`](http://eslint.org/docs/rules/no-proto)

  ```js
  const foo = obj.__proto__               // ✗ 悪い例
  const foo = Object.getPrototypeOf(obj)  // ✓ 良い例
  ```

* **変数を再宣言してはいけません。**

  eslint: [`no-redeclare`](http://eslint.org/docs/rules/no-redeclare)

  ```js
  let name = 'John'
  let name = 'Jane'     // ✗ 悪い例

  let name = 'John'
  name = 'Jane'         // ✓ 良い例
  ```

* **正規表現リテラルでは、複数の空白を避けます。**

  eslint: [`no-regex-spaces`](http://eslint.org/docs/rules/no-regex-spaces)

  ```js
  const regexp = /test   value/   // ✗ 悪い例

  const regexp = /test {3}value/  // ✓ 良い例
  const regexp = /test value/     // ✓ 良い例
  ```

* **returnステートメントでの代入は括弧で囲みます。**

  eslint: [`no-return-assign`](http://eslint.org/docs/rules/no-return-assign)

  ```js
  function sum (a, b) {
    return result = a + b     // ✗ 悪い例
  }

  function sum (a, b) {
    return (result = a + b)   // ✓ 良い例
  }
  ```

* **変数に自身を代入することは避けます。**

  eslint: [`no-self-assign`](http://eslint.org/docs/rules/no-self-assign)

  ```js
  name = name   // ✗ 悪い例
  ```

* **変数を自身と比較することは避けます。**

  eslint: [`no-self-compare`](http://eslint.org/docs/rules/no-self-compare)

  ```js
  if (score === score) {}   // ✗ 悪い例
  ```

* **カンマ演算子は使用しません。**

  eslint: [`no-sequences`](http://eslint.org/docs/rules/no-sequences)

  ```js
  if (doSomething(), !!test) {}   // ✗ 悪い例
  ```

* **制限された名前を暗示してはいけません。**

  eslint: [`no-shadow-restricted-names`](http://eslint.org/docs/rules/no-shadow-restricted-names)

  ```js
  let undefined = 'value'     // ✗ 悪い例
  ```

* **空白を含む配列を使用しません。**

  eslint: [`no-sparse-arrays`](http://eslint.org/docs/rules/no-sparse-arrays)

  ```js
  let fruits = ['apple',, 'orange']       // ✗ 悪い例
  ```

* **タブを使用してはいけません。**

  eslint: [`no-tabs`](http://eslint.org/docs/rules/no-tabs)

* **通常の文字列には、テンプレートリテラルプレースホルダーを含めません。**

  eslint: [`no-template-curly-in-string`](http://eslint.org/docs/rules/no-template-curly-in-string)

  ```js
  const message = 'Hello ${name}'   // ✗ 悪い例
  const message = `Hello ${name}`   // ✓ 良い例
  ```

* **`this`を使用する前に`super()`を呼ばなくてはなりません。**

  eslint: [`no-this-before-super`](http://eslint.org/docs/rules/no-this-before-super)

  ```js
  class Dog extends Animal {
    constructor () {
      this.legs = 4     // ✗ 悪い例
      super()
    }
  }
  ```

* **`throw`が送るのは`Error`オブジェクトのみです。**

  eslint: [`no-throw-literal`](http://eslint.org/docs/rules/no-throw-literal)

  ```js
  throw 'error'               // ✗ 悪い例
  throw new Error('error')    // ✓ 良い例
  ```

* **行末にスペースを使用してはいけません。**

  eslint: [`no-trailing-spaces`](http://eslint.org/docs/rules/no-trailing-spaces)

* **`undefined`に初期化してはいけません。**

  eslint: [`no-undef-init`](http://eslint.org/docs/rules/no-undef-init)

  ```js
  let name = undefined    // ✗ 悪い例

  let name
  name = 'value'          // ✓ 良い例
  ```

* **ループに変更されない条件を用いてはいけません。**

  eslint: [`no-unmodified-loop-condition`](http://eslint.org/docs/rules/no-unmodified-loop-condition)

  ```js
  for (let i = 0; i < items.length; j++) {...}    // ✗ 悪い例
  for (let i = 0; i < items.length; i++) {...}    // ✓ 良い例
  ```

* **よりシンプルな方法がある場合は三項演算子を使用しません。**

  eslint: [`no-unneeded-ternary`](http://eslint.org/docs/rules/no-unneeded-ternary)

  ```js
  let score = val ? val : 0     // ✗ 悪い例
  let score = val || 0          // ✓ 良い例
  ```

* **`return`, `throw`, `continue`, ` break`ステートメントの後の到達不能なコードを書いてはいけません。**

  eslint: [`no-unreachable`](http://eslint.org/docs/rules/no-unreachable)

  ```js
  function doSomething () {
    return true
    console.log('never called')     // ✗ 悪い例
  }
  ```

* **`finally`ブロックに処理フローを制御するステートメントを書いてはいけません。**

  eslint: [`no-unsafe-finally`](http://eslint.org/docs/rules/no-unsafe-finally)

  ```js
  try {
    // ...
  } catch (e) {
    // ...
  } finally {
    return 42     // ✗ 悪い例
  }
  ```

* **関係演算子の左側のオペランドの否定をしてはいけません。**

  eslint: [`no-unsafe-negation`](http://eslint.org/docs/rules/no-unsafe-negation)

  ```js
  if (!key in obj) {}       // ✗ 悪い例
  if (!(key in obj)) {}     // ✓ 良い例
  ```

* **`.call()`や`.apply()`を不必要に使用してはいけません。**

  eslint: [`no-useless-call`](http://eslint.org/docs/rules/no-useless-call)

  ```js
  sum.call(null, 1, 2, 3)   // ✗ 悪い例
  ```

* **オブジェクトで不要な処理を施したプロパティキーを使用してはいけません。**

  eslint: [`no-useless-computed-key`](http://eslint.org/docs/rules/no-useless-computed-key)

  ```js
  const user = { ['name']: 'John Doe' }   // ✗ 悪い例
  const user = { name: 'John Doe' }       // ✓ 良い例
  ```

* **不要なコンストラクタを実装しません。**

  eslint: [`no-useless-constructor`](http://eslint.org/docs/rules/no-useless-constructor)

  ```js
  class Car {
    constructor () {      // ✗ 悪い例
    }
  }
  ```

* **不要なエスケープを使用しません。**

  eslint: [`no-useless-escape`](http://eslint.org/docs/rules/no-useless-escape)

  ```js
  let message = 'Hell\o'  // ✗ 悪い例
  ```

* **importやexport、destructuring assignment(分割代入)で同じ名前に変更することはできません。**

  eslint: [`no-useless-rename`](http://eslint.org/docs/rules/no-useless-rename)

  ```js
  import { config as config } from './config'     // ✗ 悪い例
  import { config } from './config'               // ✓ 良い例
  ```

* **プロパティの前に空白を入れません。**

  eslint: [`no-whitespace-before-property`](http://eslint.org/docs/rules/no-whitespace-before-property)

  ```js
  user .name      // ✗ 悪い例
  user.name       // ✓ 良い例
  ```

* **`with`ステートメントを使用してはいけません。**

  eslint: [`no-with`](http://eslint.org/docs/rules/no-with)

  ```js
  with (val) {...}    // ✗ 悪い例
  ```

* **オブジェクトのプロパティと改行の一貫性を維持します。**

  eslint: [`object-property-newline`](http://eslint.org/docs/rules/object-property-newline)

  ```js
  const user = {
    name: 'Jane Doe', age: 30,
    username: 'jdoe86'            // ✗ 悪い例
  }

  const user = { name: 'Jane Doe', age: 30, username: 'jdoe86' }    // ✓ 良い例

  const user = {
    name: 'Jane Doe',
    age: 30,
    username: 'jdoe86'
  }                                                                 // ✓ 良い例
  ```

* **ブロック内をパディングしません。**

  eslint: [`padded-blocks`](http://eslint.org/docs/rules/padded-blocks)

  ```js
  if (user) {
                              // ✗ 悪い例
    const name = getName()

  }

  if (user) {
    const name = getName()    // ✓ 良い例
  }
  ```

* **スプレッド演算子と式の間にはスペースを入れません。**

  eslint: [`rest-spread-spacing`](http://eslint.org/docs/rules/rest-spread-spacing)

  ```js
  fn(... args)    // ✗ 悪い例
  fn(...args)     // ✓ 良い例
  ```

* **セミコロンは後ろにスペースを置いて、前にはスペースを入れません。**

  eslint: [`semi-spacing`](http://eslint.org/docs/rules/semi-spacing)

  ```js
  for (let i = 0 ;i < items.length ;i++) {...}    // ✗ 悪い例
  for (let i = 0; i < items.length; i++) {...}    // ✓ 良い例
  ```

* **ブロックの前にはスペースを入れます。**

  eslint: [`space-before-blocks`](http://eslint.org/docs/rules/space-before-blocks)

  ```js
  if (admin){...}     // ✗ 悪い例
  if (admin) {...}    // ✓ 良い例
  ```

* **括弧の内側にはスペースを入れません。**

  eslint: [`space-in-parens`](http://eslint.org/docs/rules/space-in-parens)

  ```js
  getName( name )     // ✗ 悪い例
  getName(name)       // ✓ 良い例
  ```

* **単項演算子の後にはスペースを入れます。**

  eslint: [`space-unary-ops`](http://eslint.org/docs/rules/space-unary-ops)

  ```js
  typeof!admin        // ✗ 悪い例
  typeof !admin        // ✓ 良い例
  ```

* **コメントの内側にはスペースを入れます。**

  eslint: [`spaced-comment`](http://eslint.org/docs/rules/spaced-comment)

  ```js
  //comment           // ✗ 悪い例
  // comment          // ✓ 良い例

  /*comment*/         // ✗ 悪い例
  /* comment */       // ✓ 良い例
  ```

* **テンプレート文字列にはスペースを入れません。**

  eslint: [`template-curly-spacing`](http://eslint.org/docs/rules/template-curly-spacing)

  ```js
  const message = `Hello, ${ name }`    // ✗ 悪い例
  const message = `Hello, ${name}`      // ✓ 良い例
  ```

* **`NaN`をチェックする際は`isNaN()`を使用します。**

  eslint: [`use-isnan`](http://eslint.org/docs/rules/use-isnan)

  ```js
  if (price === NaN) { }      // ✗ 悪い例
  if (isNaN(price)) { }       // ✓ 良い例
  ```

* **`typeof`は有効な文字列と比較しなければなりません。**

  eslint: [`valid-typeof`](http://eslint.org/docs/rules/valid-typeof)

  ```js
  typeof name === 'undefimed'     // ✗ 悪い例
  typeof name === 'undefined'     // ✓ 良い例
  ```

* **即時実行関数(IIFE)は括弧で囲みます。**

  eslint: [`wrap-iife`](http://eslint.org/docs/rules/wrap-iife)

  ```js
  const getName = function () { }()     // ✗ 悪い例

  const getName = (function () { }())   // ✓ 良い例
  const getName = (function () { })()   // ✓ 良い例
  ```

* **`yield*`式の`*`は前後にスペースを入れます。**

  eslint: [`yield-star-spacing`](http://eslint.org/docs/rules/yield-star-spacing)

  ```js
  yield* increment()    // ✗ 悪い例
  yield * increment()   // ✓ 良い例
  ```

* **Yoda条件式は避けます。**

  eslint: [`yoda`](http://eslint.org/docs/rules/yoda)

  ```js
  if (42 === age) { }    // ✗ 悪い例
  if (age === 42) { }    // ✓ 良い例
  ```

## セミコロン

* セミコロンは使用しません。(参考: [1](http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding), [2](http：//inimino.org/%7Einimino/blog/javascript_semicolons), [3](https://www.youtube.com/watch?v=gsfbh17Ax9I))

  eslint: [`semi`](http://eslint.org/docs/rules/semi)

  ```js
  window.alert('hi')   // ✓ 良い例
  window.alert('hi');  // ✗ 悪い例
  ```

* `(`, `[`, `` ` ``, もしくはあまり無いですがそういったもので行を開始しないでください。

  これはセミコロンを省略した場合の唯一の問題であり、`standard`はこの潜在的な問題からあなたを守ります。

  (すべてのリスト: `[`, `(`, `` ` ``, `+`, `*`, `/`, `-`, `,`, `.` - これらのほとんどは実際のコードで行頭に書くことはありません。)

  eslint: [`no-unexpected-multiline`](http://eslint.org/docs/rules/no-unexpected-multiline)

  ```js
  // ✓ 良い例
  ;(function () {
    window.alert('ok')
  }())

  // ✗ 悪い例
  (function () {
    window.alert('ok')
  }())
  ```

  ```js
  // ✓ 良い例
  ;[1, 2, 3].forEach(bar)

  // ✗ 悪い例
  [1, 2, 3].forEach(bar)
  ```

  ```js
  // ✓ 良い例
  ;`hello`.indexOf('o')

  // ✗ 悪い例
  `hello`.indexOf('o')
  ```

  ノート: このようなコードを書いていると、もっとうまい方法を試したいかもしれません。

  可能な限り明確で読みやすいコードを支持するならば、うまい短縮記述は推奨されません。

  次のようなコードについては、

  ```js
  ;[1, 2, 3].forEach(bar)
  ```

  次のように書くことが強く推奨されます。

  ```js
  var nums = [1, 2, 3]
  nums.forEach(bar)
  ```

## 参考になる読み物

- [An Open Letter to JavaScript Leaders Regarding Semicolons][1]
- [JavaScript Semicolon Insertion – Everything you need to know][2]

##### 参考になる映像:

- [Are Semicolons Necessary in JavaScript? - YouTube][3]

現在よく使用されているすべてのコードminifierは、AST-based minificationを使用するので、セミコロンがないJavaScriptを何の問題もなく処理することができます。(JavaScriptにはセミコロンは必要ではありませんので)

##### *["An Open Letter to JavaScript Leaders Regarding Semicolons"][1]* からの抜粋:

> [Relying on automatic semicolon insertion] is quite safe, and perfectly valid JS that every browser understands. Closure compiler, yuicompressor, packer, and jsmin all can properly minify it. There is no performance impact anywhere.
>
> I am sorry that, instead of educating you, the leaders in this language community have given you lies and fear.  That was shameful. I recommend learning how statements in JS are actually terminated (and in which cases they are not terminated), so that you can write code that you find beautiful.
>
> In general, `\n` ends a statement unless:
>   1. The statement has an unclosed paren, array literal, or object literal or ends in some
>      other way that is not a valid way to end a statement. (For instance, ending with `.`
>      or `,`.)
>   2. The line is `--` or `++` (in which case it will decrement/increment the next token.)
>   3. It is a `for()`, `while()`, `do`, `if()`, or `else`, and there is no `{`
>   4. The next line starts with `[`, `(`, `+`, `*`, `/`, `-`, `,`, `.`, or some other
>      binary operator that can only be found between two tokens in a single expression.
>
> The first is pretty obvious. Even JSLint is ok with `\n` chars in JSON and parenthesized constructs, and with `var` statements that span multiple lines ending in `,`.
>
> The second is super weird. I’ve never seen a case (outside of these sorts of conversations) where you’d want to do write `i\n++\nj`, but, point of fact, that’s parsed as `i; ++j`, not `i++; j`.
>
> The third is well understood, if generally despised. `if (x)\ny()` is equivalent to `if (x) { y() }`. The construct doesn’t end until it reaches either a block, or a statement.
>
> `;` is a valid JavaScript statement, so `if(x);` is equivalent to `if(x){}` or, “If x, do nothing.” This is more commonly applied to loops where the loop check also is the update function. Unusual, but not unheard of.
>
> The fourth is generally the fud-inducing “oh noes, you need semicolons!” case. But, as it turns out, it’s quite easy to *prefix* those lines with semicolons if you don’t mean them to be continuations of the previous line. For example, instead of this:
>
> ```js
> foo();
> [1,2,3].forEach(bar);
> ```
>
> you could do this:
>
> ```js
> foo()
> ;[1,2,3].forEach(bar)
> ```
>
> The advantage is that the prefixes are easier to notice, once you are accustomed to never seeing lines starting with `(` or `[` without semis.

[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons
[3]: https://www.youtube.com/watch?v=gsfbh17Ax9I
