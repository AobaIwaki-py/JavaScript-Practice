# JavaScript入門

- JavaScriptの基礎について学ぶ

## 成果物

学習の成果を確かめるために作成したものと習得した技術

- [Pokemon APIを利用したポケモン検索サイト - GitHub](https://github.com/AobaIwaki-py/Pokemon-Dictionary)
  - HTMLからJSへ入力の受け渡し
  - JSで検索対象のポケモンの情報を取得
  - JSでHTMLを作成し返却

## 参考

- [【初心者向け入門】JavaScriptの基礎 - Qiita](https://qiita.com/ab-boy_ringo/items/23f60e051e3022f2a599)
- [HTMLとJavaScriptの連携 - Qiita](https://qiita.com/Teach/items/4b0104847be9f2960665)
- [JavascriptのFetch APIを使ってJSONを取得する。 - Qiita](https://qiita.com/tarch710/items/91b8abc124a7efbc7a93)
- [フェッチ API の使用 - Web API | MDN](https://developer.mozilla.org/ja/docs/Web/API/Fetch_API/Using_Fetch)
- [HTML + CSS を初心者に教えてみた - Qiita](https://qiita.com/pure-adachi/items/1498e40d5ccc962c0765)

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
    <!-- 以下は、HTML内部にJSを書く方法 -->
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

    <!-- 以下は、app.jsから関数を読む方法 -->
    <!-- <script src="./app.js"></script> -->

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

## Mathオブジェクト

- 数学に関する関数がまとめられている

```js
// Example
Math.round(2.4)
```

## 文字列長

```js
var personName="山田太郎";
document.write(personName.length);
// 4
```

## 指定文字列の先頭の位置

```js
//指定文字列の先頭位置
var a="ABCabc012".indexOf("ABC"); //先頭から0番目(1文字目)を返す
document.write("a=\"ABCabc012\".indexOf(\"ABC\") : ",a);
// a="ABCabc012".indexOf("ABC") : 0
```

## 文字列の抽出

- 文字列から指定した位置の1文字を取得：`.charAt()`
- 文字列から指定区間の文字列を取得：`.substring()`
```js
//指定位置の文字列
var d="ABCabc012".charAt();   //先頭の文字を返す
document.write("d=\"ABCabc012\".charAt() : ",d);
// d="ABCabc012".charAt() : A
//指定位置から指定位置までの文字列
var g="ABCabc012".substring(2,5); //2番目(3文字目)から5-1番目(6-1文字目)までの文字列を返す
document.write("g=\"ABCabc012\".substring(2,5) : ",g);
// g="ABCabc012".substring(2,5) : Cab
```

## 文字列の一致確認

```js
//文字列一致( == は使用しないこと)
var i="ABCabc012".match("ABCabc012"); //一致の場合，文字列を返す
document.write("i=\"ABCabc012\".match(\"ABCabc012\") : ",i);
// i="ABCabc012".match("ABCabc012") : ABCabc012
var j="ABCabc012".match("ABCxyz012"); //不一致の場合，nullを返す
document.write("j=\"ABCabc012\".match(\"ABCxyz012\") : ", j);
// j="ABCabc012".match("ABCxyz012") : null
```

## 浅いコピーと深いコピー

- JavaScriptにおける浅いコピー
- `.concat()`を用いた深いコピー

```js
// 浅いコピーと深いコピー
var a=[1,2,3,4,5];
var b=[1,2,3,4,5];
document.write("コピー前のaとb");
document.write("<br>");
document.write("a : ",a);
document.write("<br>");
document.write("b : ",b);
document.write("<br>");
// コピー前のaとb
// a : 1,2,3,4,5
// b : 1,2,3,4,5
var shallow_copy_a=[];
var deep_copy_b=[];
shallow_copy_a = a;
shallow_copy_a.push(6);
document.write("浅いコピーの後のaとshallow_copy_a");
document.write("<br>");
document.write("a : ",a);
document.write("<br>");
document.write("shallow_copy_a : ",shallow_copy_a);
document.write("<br>");
// 浅いコピーの後のaとshallow_copy_a
// a : 1,2,3,4,5,6
// shallow_copy_a : 1,2,3,4,5,6
shallow_copy_b = b.concat();
shallow_copy_b.push(6);
document.write("深いコピーの後のbとdeep_copy_b");
document.write("<br>");
document.write("b : ",b);
document.write("<br>");
document.write("shallow_copy_b : ",shallow_copy_b);
document.write("<br>");
// 深いコピーの後のbとdeep_copy_b
// b : 1,2,3,4,5
// shallow_copy_b : 1,2,3,4,5,6
```

## Arrayオブジェクト

- 通常の配列定義
- Arrayオブジェクトによる配列定義
- 数値型を文字列へ変換
- 末端の要素を削除
- 末尾へ要素を追加
- 要素を逆順にする
- 配列の結合

```js
// 通常の配列定義
var a=[3,7,0,-5,1];
document.write(a);//区切り文字であるカンマを含め，要素全表示
// 3,7,0,-5,1

// Arrayオブジェクトによる配列定義
var a = new Array(-3,-2,-1,0,1,2,3);
document.write(a);
// -3,-2,-1,0,1,2,3

//数値から文字列(配列)へ変換
var a=314159265;
var len=a.toString().length;
document.write(a+" は "+len+" 桁");
// 314159265 は 9 桁

//末尾の要素削除
var a=[3,5,-7,2,1];
a.pop(); //末尾の要素1を削除
document.write(a);
// 3,5,-7,2

//末尾へ指定要素追加
var a=[3,5,-7,2,1];
a.push(33);
document.write(a);
// 3,5,-7,2,1,33

//要素の逆順
var a=[3,5,-7,2,1];
a.reverse();
document.write("reverse : ",a);
// 1,2,-7,5,3

//配列の結合
var a=[3,-4,0];
var b=[-7,3,1];
var c=a.concat(b);    //配列aの後ろにbを結合
document.write("concat : ",c);    //要素全表示
// 3,-4,0,-7,3,1
```

## Dateオブジェクト

- 現在時刻の取得
- Dateオブジェクトを用いて、時刻の指定
```js
//取得
var date = new Date();
var Y=date.getFullYear();      //年
var M=date.getMonth()+1;       //月(0~11)
var D=date.getDate();          //日
var w=date.getDay();           //曜日(0~6)
var week = ['SUN', "MON", "TUE", "WED", "THU", "FRI", "SAT"]
var h=date.getHours();         //時
var m=date.getMinutes();       //分
var s=date.getSeconds();       //秒
var ms=date.getMilliseconds(); //ミリ秒

document.write(Y,"/",M,"/",D,"/",week[w],":",h,":",m,":",s,".",ms);
// 2023/2/26/SUN:13:18:25.769

//指定
var date = new Date(2020,0,31,13,30,00); //2020年1月31日 13時30分00秒
document.write(date);
document.write("<br>");
// Fri Jan 31 2020 13:30:00 GMT+0900 (日本標準時)
```