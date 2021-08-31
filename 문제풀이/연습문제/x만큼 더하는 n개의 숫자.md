![image](https://user-images.githubusercontent.com/87289383/131509706-3b1a6bc7-9650-4924-a99c-f64e12905750.png)

#### 나의 풀이)
```javascript
let solution=(x,n)=> Array(n).fill(0).map((a,b)=>b*x+x)
```

#### 다른 사람 풀이)
- `Array(n).keys()`
```javascript
function solution(x, n) {
    return [...Array(n).keys()].map(v => (v + 1) * x);
}
```

#### 다른 사람 풀이)
- `Array.from({length: n},(v,index)=>`
```javascript
function solution(x, n) {
    return nNumbers(x,n);
}
const nNumbers = (x, n)=>{
    return Array.from({length: n},(v,index)=>(index+1)*x);
};
```
