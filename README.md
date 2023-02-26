# JavaScript入門

- JavaScriptの基礎について学ぶ

## 参考

- [【初心者向け入門】JavaScriptの基礎 - Qiita](https://qiita.com/ab-boy_ringo/items/23f60e051e3022f2a599)


## ダイアログを用いたユーザー認証

- サンプルコード
  - アクセス時に表示されるプロンプトに名前を入力すると、ユーザ認証が行われる。

`dialog-auth.html`
```html
<script>
    alert("このサイトは信用できません");
    var con = confirm("接続していいですか？");
    var pro = prompt("名前を入力してください");
    
    if(con){
        alert("You entered \"" + pro + "\".");
    }
    else{
        alert("You didn't enterd.")
    }
    
    if(pro=="name"){
        document.write("認証されたユーザです");
        document.write("<br>");
        document.write("(You chose \"OK\".)");
    }
    else{
        document.write("ユーザーが存在しません");
        document.write("<br>");
        document.write("(You chose \"Cancel\".)");
    }

</script>
```

## クリックやホバー時の動作

- サンプルコード
  -  クリック時にアラートを表示する方法
  -  クリック時に関数を呼び出す方法
  -  ダブルクリック、ホバー

`click-hover.html`
```html
<body>
    <script>
        function btn2()
        {
            alert("2: ログインしますか？");
        }

        function btn4()
        {
            alert("4 : 実行しますか？");
        }
    </script>

    <!-- onclick="" 内の命令が1つの場合はセミコロン省略可能 -->
    <!-- onclick･･･1回押されたら -->
    <input type="submit" value="1 : アラートを表示(クリック)" onclick="alert('1 : このボタンに現在機能はありません')">
    <br>
    <input type="submit" value="2 : ログイン確認(クリック)" onclick="btn2()">
    <br>
    <!-- ondblclick･･･2回連続して押されたら -->
    <input type="submit" value="3 : アラートを表示(ダブルクリック)" ondblclick="alert('3 : このボタンに現在機能はありません');">
    <br>
    <input type="submit" value="4 : 実行確認(ダブルクリック)" ondblclick="btn4()">
    <br>
    <!-- onmouseover･･･マウスカーソルを重ねたら -->
    <input type="submit" value="5 : ホバーで詳細を表示" onmouseover="alert('5 : 詳細な情報はありません')">
    <br>
</body>
```

## 再定義可能関数の定義

```js
<script>
    var a=10;    // 変数aの定義
    var b=5;     // 変数bの定義
    var c=7,d=1; // 複数の変数を一度に定義

    var a=3;     // 変数aの再定義
</script>
```

## 再定義不可能変数の定義

```js
<script>
    let a=10; // 変数aの定義
    let b=5;  // 変数bの定義

    let a=3;  // 変数aの再定義を試みるとエラー発生
    a=3;      // 再代入は可能
</script>
```

## 再代入不可能変数の定義

```js
<script>
    const a=10; // 変数aの定義
    const b=5;  // 変数bの定義

    const a=3;  // 変数aの再定義を試みるとエラー発生
    a=3;        // 変数aの再代入を試みてもエラー発生
</script>
```

## 配列の定義

```js
<script>
    var a = new Array("apple","orange","banana");
    var b = ["apple","orange","banana"] 

    // ブラウザによるが，コンソールで見た方がわかりやすいかも
    console.log(a); // 0:"apple", 1:"orange", 2:"banana"
    console.log(b); // 0:"apple", 1:"orange", 2:"banana"
</script>
```

## 変数の表示

```js
<script>
    var e="山田";
    document.write(`名前は${e}太郎です`);
</script>
```

## forを用いた無限ループ

```js
<script>
    for(;;){
        document.write("あいうえお<br>");
        if(jouken) break;    // 条件 jouken を満たすとき脱出
    }
</script>
```

## ダイアログ(アクセス時にポップアップで出てくる)

```js
<script>
    alert("This is Alert"); // 警告を表示[choices : OK]
    confirm("This is Confirm"); // 確認を求める[choices : OK/cancel]
    prompt("This is Prompt"); // テキストの入力を求める
</script>
```

## オブジェクト指向

```js
<script>
   //オブジェクト作成 newで作成する
   var person = new Object();
</script>
```

## オブジェクトプロトタイプ

```js
<script>
    //あらかじめ，雛形を作っておくやり方
    function person(name,email)
    {
        //thisで自身のプロパティにアクセス
        this.name=name;
        this.email=email;
    }  
    var yamada = new person("山田","yamada@hoge.hoge");
</script>
```

## 無名関数

- オブジェクトのメンバーにすることもできる

```js
<script>
    //変数に関数を代入
    var make_alert = function(){ alert("無名関数で警告を表示しています"); };

    //変数名で呼び出す
    make_alert();

    //オブジェクトのメンバーにできる
    var person = new Object();

    person.name = "yamada";
    person.email = "yamada@hoge.hoge";
    person.func_in_object = function()
    {
    document.write("オブジェクト内関数を呼び出しました");
    }

    person.func_in_object(); 
</script>
```