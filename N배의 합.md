### 놀이기구의 원래 이용료는 price원 인데, 놀이기구를 N 번 째 이용한다면 원래 이용료의 N배를 받기로 하였습니다. 즉, 처음 이용료가 100이었다면 2번째에는 200, 3번째에는 300으로 요금이 인상됩니다. 놀이기구를 count번 타게 되면 현재 자신이 가지고 있는 금액에서 얼마가 모자라는지를 return 하도록 solution 함수를 완성하세요. 단, 금액이 부족하지 않으면 0을 return 하세요.
![image](https://user-images.githubusercontent.com/87289383/129449775-bee7da5a-6022-48ec-a9d1-a7f4be45a82d.png)

#### 풀이)
- Array.from({length:count})
- map((e,idx)=>
- Array.of(str).reduce((acc,idx)=>
```javascript
function solution(price,money,count) {
    var total = 0;
    var str=[];
    str = Array.from({length:count}).map((e,idx)=>total+=(idx+1)*price);
    var val = Array.of(str).reduce((acc,x,idx)=>(acc+=x));
 return (val[val.length-1]-money)>0 ? val[val.length-1]-money : 0;
}
```

#### 풀이) 
- Array.from({length:count})
- map((e,idx)=>
- Array.of(str).map((e,idx)=>
```javascript
function solution(price,money,count) {
    var total = 0;
    var sum = 0;
    var str=[];
    var dit=[];
    str = Array.from({length:count}).map((e,idx)=>total+=(idx+1)*price);
    Array.of(str).map((e,idx)=> dit=e);
    return dit[count-1]-money>0 ? dit[count-1]-money : 0;
}
```

#### 풀이)
- Math.max
- _[0], _[1], _[2]
const solution = (..._) => { return Math.max(_[0]*_[2]*++_[2]/2-_[1],0); }

#### 풀이)
- (count+1)/2 // 가우스 공식
```javascript
function solution(price, money, count) {
    const tmp = price * count * (count + 1) / 2 - money;
    return tmp > 0 ? tmp : 0;
}
```
