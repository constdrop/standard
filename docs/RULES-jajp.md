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

* **演算子の前後** にスペースを入れます。

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

* **elseステートメント** は波括弧と同じ行に置きます。**

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
    例外: `window`, `document`, `navigator`.<br>
    `open`, `length`, `event`, `name`のような漠然とした名前を、ブラウザグローバルで偶発的に使用することを防ぎます

    ```js
    /* global alert, prompt */

    alert('hi')
    prompt('ok?')
    ```

    明示的に`window`を記述することで、その関数やプロパティを参照することはできますが、` window`の代わりに`self`を使うワーカーでは動作しません。

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

* **ファイルは、改行で終わる必要があります。**

  eslint：[ `eol-last`]（http://eslint.org/docs/rules/eol-last）

* **関数の識別子と呼び出しの間にはスペースを入れないでください。**

  eslint：[ `func-call-spacing`]（http://eslint.org/docs/rules/func-call-spacing）

  `` `js
  console.log（ 'hello'）//✗避けてください
  console.log（ 'hello'）//✓良い
  `` `

* **コロンとキーと値のペアの値の間にスペースを追加する必要があります。**

  eslint：[ `key-spacing`]（http://eslint.org/docs/rules/key-spacing）

  `` `js
  var obj = { 'key'： 'value'} //✗避けてください
  var obj = { 'key'： 'value'} //✗避けてください
  var obj = { 'key'： 'value'} //✗避けてください
  var obj = { 'key'： 'value'} //✓良い
  `` `

* **コンストラクター名前は大文字で開始する必要があります。**

  eslint：[`new-cap`]（http://eslint.org/docs/rules/new-cap）

  ```js
  function animal（）{}
  var dog= new animal（）//✗避けてください

  function Animal（）{}
  var dog= new Animal（）//✓良い
  ```

* **引数のないコンストラクタは括弧で呼び出す必要があります。**

  eslint：[`new-parens`]（http://eslint.org/docs/rules/new-parens）

  ```js
  function Animal（）{}
  var dog= new Animal//✗避けてください
  var dog= new Animal（）//✓良い
  ```

* ** setterが定義されると、オブジェクトにgetterが含まれている必要があります。**

  eslint：[`accessor-pairs`]（http://eslint.org/docs/rules/accessor-pairs）

  ```js
  var person={
    set name（value）{//✗避けてください
      this._name= value
    }
  }

  var person={
    set name（value）{
      this._name= value
    }、
    get name（）{//✓良い
      return this._name
    }
  }
  ```

* **派生クラスのコンストラクタは、`super`を呼び出す必要があります。**

  eslint：[`constructor-super`]（http://eslint.org/docs/rules/constructor-super）

  ```js
  class Dog{
    constructor（）{
      super（）//✗避けてください
    }
  }

  class Dog extends Mammal{
    constructor（）{
      super（）//✓良い
    }
  }
  ```

* **配列コンストラクタの代わりに配列リテラルを使用してください。**

  eslint：[`no-array-constructor`]（http://eslint.org/docs/rules/no-array-constructor）

  ```js
  var nums= new Array（1、2、3）//✗避けてください
  var nums=[1、2、3]//✓良い
  ```

***`arguments.callee`と` arguments.caller`を使用しないでください。**

  eslint：[`no-caller`]（http://eslint.org/docs/rules/no-caller）

  ```js
  function foo（n）{
    if（n<=0）return

    arguments.callee（n - 1）//✗避けてください
  }

  function foo（n）{
    if（n<=0）return

    foo（n - 1）//✓良い
  }
  ```

* **クラスで宣言された変数を変更しないでください**

  eslint：[ `no-class-assign`]（http://eslint.org/docs/rules/no-class-assign）

  `` `js
  class Dog {}
  Dog = 'Fido' //✗避けてください
  `` `

* ** `const`を使用して宣言された変数は、変更しないでください。**

  eslint：[ `no-const-assign`]（http://eslint.org/docs/rules/no-const-assign）

  `` `js
  const score = 100
  score = 125 //✗避けてください
  `` `

* **条件（繰り返しを除く）で定数式を使用しないでください。**

  eslint：[ `no-constant-condition`]（http://eslint.org/docs/rules/no-constant-condition）

  `` `js
  if（false）{//✗避けてください
    // ...
  }

  if（x === 0）{//✓良い
    // ...
  }

  while（true）{//✓良い
    // ...
  }
  `` `

* **正規表現には、制御文字がありません。**

  eslint：[ `no-control-regex`]（http://eslint.org/docs/rules/no-control-regex）

  `` `js
  var pattern = / \ x1f / //✗避けてください
  var pattern = / \ x20 / //✓良い
  `` `

* ** `debugger`文はありません。**

  eslint：[ `no-debugger`]（http://eslint.org/docs/rules/no-debugger）

  `` `js
  function sum（a、b）{
    debugger //✗避けてください
    return a + b
  }
  `` `

** **変数`delete`演算子はありません。**

  eslint：[`no-delete-var`]（http://eslint.org/docs/rules/no-delete-var）

  ```js
  var name
  delete name//✗避けてください
  ```

* **関数の定義時に重複した引数を使用することができません。**

  eslint：[`no-dupe-args`]（http://eslint.org/docs/rules/no-dupe-args）

  ```js
  function sum（a、b、a）{//✗避けてください
    //...
  }

  function sum（a、b、c）{//✓良い
    //...
  }
  ```

* **クラスメンバーに重複した名前を使用することができません。**

  eslint：[`no-dupe-class-members`]（http://eslint.org/docs/rules/no-dupe-class-members）

  ```js
  class Dog{
    bark（）{}
    bark（）{}//✗避けてください
  }
  ```

* **オブジェクトリテラルで重複したキーの値を使用することができません。**

  eslint：[`no-dupe-keys`]（http://eslint.org/docs/rules/no-dupe-keys）

  ```js
  var user={
    name：「Jane Doe」、
    name：「John Doe」//✗避けてください
  }
  ```

* ** `switch`ステートメントで重複している` case`ラベルを使用することができません。**

  eslint：[ `no-duplicate-case`]（http://eslint.org/docs/rules/no-duplicate-case）

  `` `js
  switch（id）{
    case 1：
      // ...
    case 1：//✗避けてください
  }
  `` `

* **モジュールごとに1つのimportステートメントを使用する必要があります。**

  eslint：[ `no-duplicate-imports`]（http://eslint.org/docs/rules/no-duplicate-imports）

  `` `js
  import {myFunc1} from「module」
  import {myFunc2} from「module」//✗避けてください

  import {myFunc1、myFunc2} from「module」//✓良い
  `` `

* **正規表現で、空の文字クラスがないはずです。**

  eslint：[ `no-empty-character-class`]（http://eslint.org/docs/rules/no-empty-character-class）

  `` `js
  const myRegex = / ^ abc [] / //✗避けてください
  const myRegex = / ^ abc [a-z] / //✓良い
  `` `

* **空の構造のパターンがないはずです。**

  eslint：[ `no-empty-pattern`]（http://eslint.org/docs/rules/no-empty-pattern）

  `` `js
  const {a：{}} = foo //✗避けてください
  const {a：{b}} = foo //✓良い
  `` `

* ** `eval（）`を使用していません。**

  eslint：[ `no-eval`]（http://eslint.org/docs/rules/no-eval）

  `` `js
  eval（ "var result = user" + propName）//✗避けてください
  var result = user [propName] //✓良い
  `` `

* ** `catch`節の例外を再割り当てしないでください。**

  eslint：[ `no-ex-assign`]（http://eslint.org/docs/rules/no-ex-assign）

  `` `js
  try {
    // ...
  } catch（e）{
    e = 'new value' //✗避けてください
  }

  try {
    // ...
  } catch（e）{
    const newVal = 'new value' //✓良い
  }
  `` `

* **ネイティブオブジェクトを拡張しません。**

  eslint：[ `no-extend-native`]（http://eslint.org/docs/rules/no-extend-native）

  `` `js
  Object.prototype.age = 21 //✗避けてください
  `` `

* **不要な関数のバインドを避ける必要があります。**

  eslint：[ `no-extra-bind`]（http://eslint.org/docs/rules/no-extra-bind）

  `` `js
  const name = function（）{
    getName（）
  } .bind（user）//✗避けてください

  const name = function（）{
    this.getName（）
  } .bind（user）//✓良い
  `` `

* **不要なbooleanキャストを避ける必要があります。**

  eslint：[ `no-extra-boolean-cast`]（http://eslint.org/docs/rules/no-extra-boolean-cast）

  `` `js
  const result = true
  if（！result）{//✗避けてください
    // ...
  }

  const result = true
  if（result）{//✓良い
    // ...
  }
  `` `

* **関数式には、不要な括弧がないことを確認します。**

  eslint：[ `no-extra-parens`]（http://eslint.org/docs/rules/no-extra-parens）

  `` `js
  const myFunc =（function（）{}）//✗避けてください
  const myFunc = function（）{} //✓良い
  `` `

* ** 'switch」の場合に完了していないことを防ぐために「break」を使用してください。**

  eslint：[ `no-fallthrough`]（http://eslint.org/docs/rules/no-fallthrough）

  `` `js
  switch（filter）{
    case 1：
      doSomething（）//✗避けてください
    case 2：
      doSomethingElse（）
  }

  switch（filter）{
    case 1：
      doSomething（）
      break //✓良い
    case 2：
      doSomethingElse（）
  }

  switch（filter）{
    case 1：
      doSomething（）
      // fallthrough //✓良い
    case 2：
      doSomethingElse（）
  }
  `` `

* **浮動小数点がないはずです。**

  eslint：[ `no-floating-decimal`]（http://eslint.org/docs/rules/no-floating-decimal）

  `` `js
  const discount = 0.5 //✗避けてください
  const discount = 0.5 //✓良い
  `` `

* **関数の宣言を再指定しないでください。**

  eslint：[ `no-func-assign`]（http://eslint.org/docs/rules/no-func-assign）

  `` `js
  function myFunc（）{}
  myFunc = myOtherFunc //✗避けてください
  `` `

* **読み取り専用のグローバル変数を上書きしないようにします。**

  eslint：[ `no-global-assign`]（http://eslint.org/docs/rules/no-global-assign）

  `` `js
  window = {} //✗避けてください
  `` `

* ** `eval（）`が含まれていないようにします。**

  eslint：[ `no-implied-eval`]（http://eslint.org/docs/rules/no-implied-eval）

  `` `js
  setTimeout（ "alert（ 'Hello world'）"）//✗避けてください
  setTimeout（function（）{alert（ 'Hello world'）}）//✓良い
  `` `

* **ブレースの中で関数が宣言されてはいけません。**

  eslint：[ `no-inner-declarations`]（http://eslint.org/docs/rules/no-inner-declarations）

  `` `js
  if（authenticated）{
    function setAuthUser（）{} //✗避けてください
  }
  `` `

* ** `RegExp`コンストラクタに誤った正規表現文字列がないはずです。**

  eslint：[ `no-invalid-regexp`]（http://eslint.org/docs/rules/no-invalid-regexp）

  `` `js
  RegExp（「[a-z '）//✗避けてください
  RegExp（「[a-z] '）//✓良い
  `` `

* **不規則なスペースがないことです。**

  eslint：[ `no-irregular-whitespace`]（http://eslint.org/docs/rules/no-irregular-whitespace）

  `` `js
  function myFunc（）/ * <NBSP> * / {} //✗避けてください
  `` `

* ** `__iterator__`を使用しないでください。**

  eslint：[ `no-iterator`]（http://eslint.org/docs/rules/no-iterator）

  `` `js
  Foo.prototype .__ iterator__ = function（）{} //✗避けてください
  `` `

* **範囲変数と名前を共有するラベルがないはずです。**

  eslint：[ `no-label-var`]（http://eslint.org/docs/rules/no-label-var）

  `` `js
  var score = 100
  function game（）{
    score：while（true）{//✗避けてください
      score - = 10
      if（score> 0）continue score
      break
    }
  }
  `` `

* **ラベルステートメントを使用しないでください。**

  eslint：[`no-labels`]（http://eslint.org/docs/rules/no-labels）

  ```js
  label：
    while（true）{
      break label//✗避けてください
    }
  ```

* **不要にネストされたブロックがないこと。**

  eslint：[`no-lone-blocks`]（http://eslint.org/docs/rules/no-lone-blocks）

  ```js
  function myFunc（）{
    {//✗避けてください
      myOtherFunc（）
    }
  }

  function myFunc（）{
    myOtherFunc（）//✓良い
  }
  ```

* **スペースやタブを混ぜて使用しないでください。**

  eslint：[`no-mixed-spaces-and-tabs`]（http://eslint.org/docs/rules/no-mixed-spaces-and-tabs）

* **インデントを除いては、複数のスペースを使用しないでください。**

  eslint：[`no-multi-spaces`]（http://eslint.org/docs/rules/no-multi-spaces）

  ```js
  const id=1234//✗避けてください
  const id=1234//✓良い
  ```

* **マルチライン文字列を使用しないでください。**

  eslint：[`no-multi-str`]（http://eslint.org/docs/rules/no-multi-str）

  ```js
  const message= 'Hello\
                   world'//✗避けてください
  ```

* **変数にオブジェクトを代入せずに`new`を使用しないでください。**

  eslint：[`no-new`]（http://eslint.org/docs/rules/no-new）

  ```js
  new Character（）//✗避けてください
  const character= new Character（）//✓良い
  ```

* **`Function`コンストラクタを使用しないでください。**

  eslint：[`no-new-func`]（http://eslint.org/docs/rules/no-new-func）

  ```js
  var sum= new Function（ 'a'、 'b'、 'return a+ b'）//✗避けてください
  ```

* **`Object`コンストラクタを使用しないでください。**

  eslint：[`no-new-object`]（http://eslint.org/docs/rules/no-new-object）

  ```js
  let config= new Object（）//✗避けてください
  ```

* ** `new require`を使用しないでください。**

  eslint：[ `no-new-require`]（http://eslint.org/docs/rules/no-new-require）

  `` `js
  const myModule = new require（ 'my-module'）//✗避けてください
  `` `

* ** `Symbol`コンストラクタを使用しないでください。**

  eslint：[ `no-new-symbol`]（http://eslint.org/docs/rules/no-new-symbol）

  `` `js
  const foo = new Symbol（ 'foo'）//✗避けてください
  `` `

* **プリミティブラッパーのインスタンスを使用しないでください。**

  eslint：[ `no-new-wrappers`]（http://eslint.org/docs/rules/no-new-wrappers）

  `` `js
  const message = new String（ 'hello'）//✗避けてください
  `` `

* **グローバルオブジェクトのプロパティを関数に呼び出さないでください。**

  eslint：[ `no-obj-calls`]（http://eslint.org/docs/rules/no-obj-calls）

  `` `js
  const math = Math（）//✗避けてください
  `` `

* ** 8進数を使用していません。**

  eslint：[ `no-octal`]（http://eslint.org/docs/rules/no-octal）

  `` `js
  const num = 042 //✗避けてください
  const num = '042' //✓良い
  `` `

* **文字列リテラルには、8進数のエスケープシーケンスがありません。**

  eslint：[ `no-octal-escape`]（http://eslint.org/docs/rules/no-octal-escape）

  `` `js
  const copyright = 'Copyright \ 251' //✗避けてください
  `` `

* ** `__dirname`と` __filename`を使用するときに文字列の連結を避ける必要があります。**

  eslint：[ `no-path-concat`]（http://eslint.org/docs/rules/no-path-concat）

  `` `js
  const pathToFile = __dirname + '/app.js' //✗避けてください
  const pathToFile = path.join（__ dirname、「app.js '）//✓良い
  `` `

* ** `__proto__`使用は避けてください。**の代わりに` getPrototypeOf`を使用することができます。

  eslint：[ `no-proto`]（http://eslint.org/docs/rules/no-proto）

  `` `js
  const foo = obj .__ proto__ //✗避けてください
  const foo = Object.getPrototypeOf（obj）//✓良い
  `` `

* **変数を新たに上書きしないようにします。**

  eslint：[ `no-redeclare`]（http://eslint.org/docs/rules/no-redeclare）

  `` `js
  let name = 'John'
  let name = 'Jane' //✗避けてください

  let name = 'John'
  name = 'Jane' //✓良い
  `` `

* **正規表現リテラルでは、空白を避ける必要があります。**

  eslint：[ `no-regex-spaces`]（http://eslint.org/docs/rules/no-regex-spaces）

  `` `js
  const regexp = / test value / //✗避けてください

  const regexp = / test {3} value / //✓良い
  const regexp = / test value / //✓良い
  `` `

* **リターン内容の代入値は括弧で囲む必要があります。**

  eslint：[`no-return-assign`]（http://eslint.org/docs/rules/no-return-assign）

  ```js
  function sum（a、b）{
    return result= a + b//✗避けてください
  }

  function sum（a、b）{
    return（result= a + b）//✓良い
  }
  ```

* **変数自体に自分自身は、割り当てられていません。**

  eslint：[`no-self-assign`]（http://eslint.org/docs/rules/no-self-assign）

  ```js
  name= name//✗避けてください
  ```

* **変数を自分自身と比較しないでください。**

  eslint：[`no-self-compare`]（http://eslint.org/docs/rules/no-self-compare）

  ```js
  if（score=== score）{}//✗避けてください
  ```

* **カンマ演算子を使用しないでください。**

  eslint：[`no-sequences`]（http://eslint.org/docs/rules/no-sequences）

  ```js
  if（doSomething（）、!! test）{}//✗避けてください
  ```

* **限られた名前をシェーディングいけません。**

  eslint：[ `no-shadow-restricted-names`]（http://eslint.org/docs/rules/no-shadow-restricted-names）

  `` `js
  let undefined = 'value' //✗避けてください
  `` `

* **空白の配列は許可されません。**

  eslint：[ `no-sparse-arrays`]（http://eslint.org/docs/rules/no-sparse-arrays）

  `` `js
  let fruits = [ 'apple'; 'orange'] //✗避けてください
  `` `

* **]タブを使用してはいけません。**

  eslint：[ `no-tabs`]（http://eslint.org/docs/rules/no-tabs）

* **通常の文字列には、テンプレートリテラルプレースホルダないはずです。**

  eslint：[ `no-template-curly-in-string`]（http://eslint.org/docs/rules/no-template-curly-in-string）

  `` `js
  const message = 'Hello $ {name}' //✗避けてください
  const message = `Hello $ {name}` //✓良い
  `` `

* ** `this`を使用する前に、` super（） `を呼び出す必要があります。**

  eslint：[ `no-this-before-super`]（http://eslint.org/docs/rules/no-this-before-super）

  `` `js
  class Dog extends Animal {
    constructor（）{
      this.legs = 4 //✗避けてください
      super（）
    }
  }
  `` `

* **必ず `throw`は` Error`オブジェクトである必要があります。**

  eslint：[ `no-throw-literal`]（http://eslint.org/docs/rules/no-throw-literal）

  `` `js
  throw 'error' //✗避けてください
  throw new Error（ 'error'）//✓良い
  `` `

* **行末にスペースを使用することができません。**

  eslint：[ `no-trailing-spaces`]（http://eslint.org/docs/rules/no-trailing-spaces）

* ** 'undefined」に初期化することはできません。**

  eslint：[ `no-undef-init`]（http://eslint.org/docs/rules/no-undef-init）

  `` `js
  let name = undefined //✗避けてください

  let name
  name = 'value' //✓良い
  `` `

* **ループで修正することができない条件があっています。**

  eslint：[ `no-unmodified-loop-condition`]（http://eslint.org/docs/rules/no-unmodified-loop-condition）

  `` `js
  for（let i = 0; i <items.length; j ++）{...} //✗避けてください
  for（let i = 0; i <items.length; i ++）{...} //✓良い
  `` `

* **より簡単な代替があるとき三項演算子を使用していません。**

  eslint：[ `no-unneeded-ternary`]（http://eslint.org/docs/rules/no-unneeded-ternary）

  `` `js
  let score = val？ val：0 //✗避けてください
  let score = val || 0 //✓良い
  `` `

* ** `return`、` throw`、 `continue`、` break`ステートメントの後に到達することができないコードはありません。**

  eslint：[ `no-unreachable`]（http://eslint.org/docs/rules/no-unreachable）

  `` `js
  function doSomething（）{
    return true
    console.log（ 'never called'）//✗避けてください
  }
  `` `

* ** `finally`ブロックに流れを制御することができるステートメントがないはずです。**

  eslint：[ `no-unsafe-finally`]（http://eslint.org/docs/rules/no-unsafe-finally）

  `` `js
  try {
    // ...
  } catch（e）{
    // ...
  } finally {
    return 42 //✗避けてください
  }
  `` `

* **関係演算子の左側のオペランドを否定してはいけません。**

  eslint：[ `no-unsafe-negation`]（http://eslint.org/docs/rules/no-unsafe-negation）

  `` `js
  if（！key in obj）{} //✗避けてください
  if（！（key in obj））{} //✓良い
  `` `

* ** `.call（）`と `.apply（）`を不必要に使用しないでください。**

  eslint：[ `no-useless-call`]（http://eslint.org/docs/rules/no-useless-call）

  `` `js
  sum.call（null、1、2、3）//✗避けてください
  `` `

* **オブジェクトで不要に計算された属性のキーを使用しないでください。**

  eslint：[ `no-useless-computed-key`]（http://eslint.org/docs/rules/no-useless-computed-key）

  `` `js
  const user = {[ 'name']：「John Doe」} //✗避けてください
  const user = {name： "John Doe '} //✓良い
  `` `

* **不要なコンストラクタがないことを確認します**

  eslint：[ `no-useless-constructor`]（http://eslint.org/docs/rules/no-useless-constructor）

  `` `js
  class Car {
    constructor（）{//✗避けてください
    }
  }
  `` `

* **不要なエスケープがないことを確認します。**

  eslint：[ `no-useless-escape`]（http://eslint.org/docs/rules/no-useless-escape）

  `` `js
  let message = 'Hell \ o' //✗避けてください
  `` `

* ** import、exportと消滅した割り当ての名前を同じ名前に変えることはできません。**

  eslint：[ `no-useless-rename`]（http://eslint.org/docs/rules/no-useless-rename）

  `` `js
  import {config as config} from「./config '//✗避けてください
  import {config} from「./config '//✓良い
  `` `

* **属性の前に空白がないこと。**

  eslint：[ `no-whitespace-before-property`]（http://eslint.org/docs/rules/no-whitespace-before-property）

  `` `js
  user .name //✗避けてください
  user.name //✓良い
  `` `

* `with`ステートメントを使用していません。**

  eslint：[ `no-with`]（http://eslint.org/docs/rules/no-with）

  `` `js
  with（val）{...} //✗避けてください
  `` `

* **オブジェクトのプロパティとの間の一貫性を維持します。**

  eslint：[ `object-property-newline`]（http://eslint.org/docs/rules/object-property-newline）

  `` `js
  const user = {
    name：「Jane Doe」、age：30、
    username：「jdoe86 '//✗避けてください
  }

  const user = {name： "Jane Doe」、age：30、username：「jdoe86 '} //✓良い

  const user = {
    name：「Jane Doe」、
    age：30、
    username：「jdoe86」
  } //✓良い
  `` `

* **ブロック内のパディングがないはずです。**

  eslint：[ `padded-blocks`]（http://eslint.org/docs/rules/padded-blocks）

  `` `js
  if（user）{
                              //✗避けてください
    const name = getName（）

  }

  if（user）{
    const name = getName（）//✓良い
  }
  `` `

* **スプレッド演算子と式の間にスペースがないです。**

  eslint：[ `rest-spread-spacing`]（http://eslint.org/docs/rules/rest-spread-spacing）

  `` `js
  fn（... args）//✗避けてください
  fn（... args）//✓良い
  `` `

* **セミコロンは後ろにスペースを置いて前方にスペースを入れないようにします。**

  eslint：[ `semi-spacing`]（http://eslint.org/docs/rules/semi-spacing）

  `` `js
  for（let i = 0; i <items.length; i ++）{...} //✗避けてください
  for（let i = 0; i <items.length; i ++）{...} //✓良い
  `` `

* **ブロックの前にスペースが必要です。**

  eslint：[ `space-before-blocks`]（http://eslint.org/docs/rules/space-before-blocks）

  `` `js
  if（admin）{...} //✗避けてください
  if（admin）{...} //✓良い
  `` `

* **括弧内のスペースがないことです。**

  eslint：[ `space-in-parens`]（http://eslint.org/docs/rules/space-in-parens）

  `` `js
  getName（name）//✗避けてください
  getName（name）//✓良い
  `` `

* **単項演算子の後にスペースが必要です。**

  eslint：[ `space-unary-ops`]（http://eslint.org/docs/rules/space-unary-ops）

  `` `js
  typeof！admin //✗避けてください
  typeof！admin //✓良い
  `` `

* **コメントの中には、スペースを使用する必要があります。**

  eslint：[ `spaced-comment`]（http://eslint.org/docs/rules/spaced-comment）

  `` `js
  // comment //✗避けてください
  // comment //✓良い

  / * comment * / //✗避けてください
  / * comment * / //✓良い
  `` `

* **テンプレート文字列には、間隔がありません。**

  eslint：[ `template-curly-spacing`]（http://eslint.org/docs/rules/template-curly-spacing）

  `` `js
  const message = `Hello、$ {name}` //✗避けてください
  const message = `Hello、$ {name}` //✓良い
  `` `

* ** `NaN`をチェックするときに` isNaN（） `を使用してください。**

  eslint：[ `use-isnan`]（http://eslint.org/docs/rules/use-isnan）

  `` `js
  if（price === NaN）{} //✗避けてください
  if（isNaN（price））{} //✓良い
  `` `

* ** `typeof`は、有効な文字列と比較する必要があります。**

  eslint：[ `valid-typeof`]（http://eslint.org/docs/rules/valid-typeof）

  `` `js
  typeof name ===「undefimed '//✗避けてください
  typeof name ===「undefined」//✓良い
  `` `

* **すぐ呼び出された関数式（IIFE）は改行されます。**

  eslint：[ `wrap-iife`]（http://eslint.org/docs/rules/wrap-iife）

  `` `js
  const getName = function（）{}（）//✗避けてください

  const getName =（function（）{}（））//✓良い
  const getName =（function（）{}）（）//✓良い
  `` `

* **`yield*`式の`*'は前後にスペースが必要です。**

  eslint：[`yield-star-spacing`]（http://eslint.org/docs/rules/yield-star-spacing）

  ```js
  yield* increment（）//✗避けてください
  yield* increment（）//✓良い
  ```

* ** Yoda条件を避けてください。**

  eslint：[`yoda`]（http://eslint.org/docs/rules/yoda）

  ```js
  if（42=== age）{}//✗避けてください
  if（age===42）{}//✓良い
  ```

##セミコロン

* セミコロンは使用しません。（観光：[1]（http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding）、[2]（http：//inimino.org/%7Einimino/blog/javascript_semicolons）、[3]（https://www.youtube.com/watch?v=gsfbh17Ax9I））

  eslint：[`semi`]（http://eslint.org/docs/rules/semi）

  ```js
  window.alert（ 'hi'）//✓良い
  window.alert（ 'hi'）;//✗避けてください
  ```

* `（ '、' [`、or `` `` `を使用して行を開始しないでください。これは、セミコロンを省略した唯一の試みであり、standardは、この潜在的な問題からあなたを保護します。

  eslint：[ `no-unexpected-multiline`]（http://eslint.org/docs/rules/no-unexpected-multiline）

  `` `js
  //✓良い
  ;（function（）{
    window.alert（ 'ok'）
  }（））

  //✗避けてください
  （function（）{
    window.alert（ 'ok'）
  }（））
  `` `

  `` `js
  //✓良い
  ; [1、2、3] .forEach（bar）

  //✗避けてください
  [1、2、3] .forEach（bar）
  `` `

  `` `js
  //✓良い
  ; `hello`.indexOf（ 'o'）

  //✗避けてください
  `hello`.indexOf（ 'o'）
  `` `

  注：もし、多くの場合、このようなコードを書く場合には、営利てなろうと努力するかもしれません。

  賢いビーグルは、可能な限り明確で読みやすい表現を好む。

  次のような利点があります。

  `` `js
  ; [1、2、3] .forEach（bar）
  `` `

  これは強力に好む。

  `` `js
  var nums = [1、2、3]
  nums.forEach（bar）
  `` `

##助けに値する読み物

- [An Open Letter to JavaScript Leaders Regarding Semicolons] [1]
- [JavaScript Semicolon Insertion - Everything you need to know] [2]

#####助けに値する映像

- [Are Semicolons Necessary in JavaScript？ - YouTube] [3]

現在使用されているすべての人気code minifiersはASTベース縮小を使用するので、何の問題もなく、セミコロンがないJavaScriptを処理することができます。 （JavaScriptではセミコロンは必要ありませんので）

##### Excerpt from * [ "An Open Letter to JavaScript Leaders Regarding Semicolons"] [1] *：

> [自動セミコロン挿入に依存]は非常に安全であり、すべてのブラウザが理解できる完全に有効なJSです。 Closureコンパイラ、yuicompressor、packerとjsminはすべて、これを適切に縮小することができます。どこパフォーマンスに影響を与えません。
>
>あなたを教育する代わりに、この言語共同体の指導者たちが嘘と恐怖を与えられたことを残念に思います。恥ずかしいことだった。 JSでの陳述がどのように実際に終了している（いくつかの場合には、終了していないかどうか）を学ぶことをお勧め。従って美しく見つけたコードを書くことができます。
>
>一般的に、 `\ n`は、次のような場合を除いては、ステートメントを終了します：
> 1.ステートメントは、閉じていないカッコ、配列リテラルまたはオブジェクトリテラルを持つか、またはステートメントを終了する有効な方法ではなく、他の方法で終了します。 （例えば、または、、で終わる）
> 2線は - または++です（この場合は、次のトークンを減少/増加させます）。
> 3. {がない場合の中でfor（）、while（）、do、if（）、elseです。
> 4.次の行は、[、（+、、*、/、、、、。、または単一の式の2つのトークンの間でのみ発見されることができる他の二項演算子で開始します。
>
>最初はかなり明白です。 JSLintさえJSONと括弧で囲まれた構造体の `\ n`文字と '、'で終わる複数行にまたがる` var`のドアもかまいません。
>
>二つ目は非常に奇妙です。私は「i \ n ++ \ nj`と書いてみたいが、（この種の対話外）解析された事実を見たことがありません。 `i; ++ j`ではなく、 `i ++; j`です。
>
>三番目は、一般的に蔑視受ける場合よく理解されます。 `if（x）\ ny（）`は `if（x）{y（）}`と同じです。構文は、ブロックや文に到達するまで終わらない。
>
> `if（x）;`は `if（x）{}`または "If x、nothing do nothing」と同じです。これは、一般的に、ループチェックが実行されるループに適用されても更新機能です。異常だが、前例がありません。
>
>第四は、一般的に「ああ、まさか、あなたはセミコロンが必要です！」という事例があります。しかし、前の行の連続でなくても、セミコロンで*接頭辞*を付けることは簡単です。たとえば、次のコードではなく、することができます。
>
> `` `js
> foo（）;
> [1,2,3] .forEach（bar）;
> `` `
>
>次のようにすることができます。
>
> `` `js
> foo（）
>; [1,2,3] .forEach（bar）
> `` `
>
>利点は、 `（`または `[`なくセミコロンで始まる行を見なければ慣れる簡単です。

[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons
[3]: https://www.youtube.com/watch?v=gsfbh17Ax9I
