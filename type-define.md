# 型定義について不満に思ってること

同じ値をもつ変数に型を定義した場合に、同じ値を何度も型に定義するのが面倒くさい。

```
let type1: 'key1' | 'key2' | 'key3' = 'key1';
let type2: 'key1' | 'key2' | 'key3' = 'key2';
```

## enum

enumを定義すれば、

```
enum Types {
    KEY_1 = 'key1',
    KEY_2 = 'key2',
    KEY_3 = 'key3'
}
```

変数の肩に定義することはできるが、

```
let type: Types = Types.KEY_1;
```

ハッシュの型にする事はできない
(型 'typeof Types' を型 'string' に割り当てることはできません。)
```
let map: {Types: string} = {
    Types.KEY_1: 'value'
}
```

## enum の値を変数に定義すれば

```
let KEY_1: Types = Types.KEY_1;
let KEY_2: Types = Types.KEY_2;
let KEY_3: Types = Types.KEY_3;

// 型 '{ KEY_1: string; }' を型 '{ Types: string; }' に割り当てることはできません。
// オブジェクト リテラルは既知のプロパティのみ指定できます。'KEY_1' は型 '{ Types: string; }' に存在しません。
let map: {Types: string} = {KEY_1: 'hoge'};
```

やっぱり無理

