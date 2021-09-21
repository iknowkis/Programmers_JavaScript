![image](https://user-images.githubusercontent.com/87289383/134202951-64292f6f-7882-4b2d-9911-38d762cd4f75.png)
![image](https://user-images.githubusercontent.com/87289383/134203044-68e51775-f701-4a48-a289-2710f9fda859.png)

#### 나의 풀이)
```javascript
function solution(lottos, win_nums) {
    let max = 0
    let min = 0
    lottos.map(a=> {
        win_nums.map(b=> a==b ? min++ : 0);
        a==0 ? max++ : 0;
    })
    return [7-min-max, 7-min].map(e=>e==7 ? 6 : e);
}
```

#### 다른 사람 풀이)
- `arr1.filter(v => arr2.includes(v))`
```javascript
function solution(lottos, win_nums) {
    const rank = [6, 6, 5, 4, 3, 2, 1];

    let minCount = lottos.filter(v => win_nums.includes(v)).length;
    let zeroCount = lottos.filter(v => !v).length;

    const maxCount = minCount + zeroCount;

    return [rank[maxCount], rank[minCount]];
}
```
