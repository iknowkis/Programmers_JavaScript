![image](https://user-images.githubusercontent.com/87289383/131881589-ceb6a258-4b0b-4410-85d2-7ccc1efd9d62.png)
![image](https://user-images.githubusercontent.com/87289383/131881742-82e227ac-9d6d-4176-b5cf-a5186cd84bad.png)
![image](https://user-images.githubusercontent.com/87289383/131881921-fe3e3198-fc9c-4856-84df-8b524e3c314e.png)
![image](https://user-images.githubusercontent.com/87289383/131881984-8217d86a-4cbf-455e-b72c-eddb739b8584.png)

#### 나의 풀이)
- ` | // 비트연산자 or`
```javascript
let solution=(n,arr1,arr2)=> arr1.map((e,i) => (e | arr2[i]).toString(2)
                                 .replace(/1/gi, '#')
                                 .replace(/0/gi, ' '))
                                 .map(v => v.length<n ? v=' '.repeat(n-v.length)+v : v)
```

#### 다른 사람 풀이)
- `.replace(/1|0/g, a => +a ? '#' : ' ')`
```javascript
function solution(n, arr1, arr2) {
    return arr1.map((v, i) => addZero(n, (v | arr2[i]).toString(2)).replace(/1|0/g, a => +a ? '#' : ' '));
}

const addZero = (n, s) => {
    return '0'.repeat(n - s.length) + s;
}
```

#### 다른 사람 풀이)
- `.padStart(n,0) // n 길이를 만족하도록 앞의 빈 자리 채우기`
```javascript
var solution=(n,a,b)=>a.map((a,i)=>(a|b[i]).toString(2).padStart(n,0).replace(/0/g,' ').replace(/1/g,'#'))
```

#### 다른 사람 풀이)
- `내장함수 사용하지 않고 풀이`
function solution(n, arr1, arr2) {
    let num1, num2, s;
    let answer = [];
    //manually turning decimals to binaries cos i can!
    for (let i=0; i<n; i++){
        num1 = arr1[i];
        num2 = arr2[i];
        s = '';
        for (let j=0; j<n; j++){
            s = (num1%2 + num2%2) ? '#'+s : ' '+s;
            num1 = Math.floor(num1/2);
            num2 = Math.floor(num2/2);
        }
        answer.push(s);
    }    
    return answer;
}
```
