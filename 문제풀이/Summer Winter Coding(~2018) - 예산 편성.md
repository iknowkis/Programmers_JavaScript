![image](https://user-images.githubusercontent.com/87289383/131880191-2cd9e3b7-0f25-493a-a52e-298844e49c83.png)

#### 나의 풀이)
```javascript
function solution(d, budget, answer=0, cnt=0) {
    d.sort((a,b)=>a-b).map(a=> answer+a<=budget ? [answer+=a,cnt++] : 0)
    return cnt
}
```
#### 다른 사람 풀이)
- ` ~ // 각 비트 NOT`
```javascript
function solution(d, budget) {
    return ~(~d.sort((a,b)=>a-b).map(v => budget -= v).findIndex(v => v < 0) || ~d.length);
}
```

#### 다른 사람 풀이)
```javascript
function solution(d, budget) {
    let answer = 0;
    let money = 0;
    d.sort((a,b) => a-b).forEach(function(val){
        money += val;
        if(money <= budget){
            answer++;    
        }
    })
    return answer;
}
```
