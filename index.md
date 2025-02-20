## 構文そのものに関するメモを書くのはダメ
```JavaScript
//ここでif文でxが10か確かめる!
if (x=10) {
 //処理    
}
```
## ネストが深くなりそうだったら  
ネストが深くなりすぎるとコードの可読性が下がるから、以下の方法で改善しよう！

### 1. **ガード節を使う**  
条件を満たさない場合は早期リターンすることで、ネストを減らせる
```javascript
function process(x) {
    if (x !== 10) return;
    // 処理
}
```

### 2. **関数に分割する**  
ネストの深い処理を別の関数に分けると、可読性が向上する
```javascript
function isValid(x) {
    return x === 10;
}

function process(x) {
    if (!isValid(x)) return;
    // 処理
}
```

### 3. **オブジェクトや配列で条件分岐を簡潔に**  
条件分岐が多い場合、オブジェクトや配列を活用するとスッキリする
```javascript
const actions = {
    10: () => { /* 処理 */ },
    20: () => { /* 別の処理 */ }
};

if (actions[x]) actions[x]();
```

### 4. **スイッチ文を活用する**  
複数の条件を分岐する場合は `switch` 文がよき！！
```javascript
switch (x) {
    case 10:
        // 処理
        break;
    case 20:
        // 別の処理
        break;
    default:
        // その他の処理
}
```
