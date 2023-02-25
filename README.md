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

# 文法
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

