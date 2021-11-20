| 문제 | 입출력 예 |
| ----- | ----- |
| ![image](https://user-images.githubusercontent.com/87289383/142730002-1f6ba493-6e5d-421c-b0c2-d639f46c6ae5.png) | ![image](https://user-images.githubusercontent.com/87289383/142730013-7b2c14df-26fc-4884-bb98-22e9507d9cb5.png) |

#### 나의 풀이)
```javascript
function solution(dart, _=0, answer= [0]) {
    for(let i=0;i<dart.length;i++) {
        let p = 0;
        
        dart[i]==1 ? (dart[i+1]==0 ? p += 10 : p += dart[i]) :
            dart[i]>=0 ? p += dart[i] : _;
         
        let n = i+1;
        if(p==10) n++;
        dart[n]=='D' && dart[i]!=0
            ? p=Math.pow(p,2)
            : dart[n]=='T' ? p=Math.pow(p,3) : _;
        
        let p_2= answer.length-2;
        let p_1= answer.length-1;
        
        p==0 && dart[i-1]==1 ? p=0 : 0
        
        dart[i]=='*' ?
            [answer[p_2] != null ?
                answer.splice(p_2,1,answer[p_2] * 2) : _
                    , answer.splice(p_1, 1, answer[p_1] * 2)] :
            dart[i]=='#' ?
                answer.splice(p_1, 1, answer[p_1] * -1) : _;
        
        p != 0 ? answer.push(+p) : _;
        
        dart[i-1]!=1 && dart[i]==0 ? answer.push(+p) : _;
    }
    return answer.reduce((a,b)=>a+b);
}
```

#### 다른 사람 풀이)
- `options = { '*': 2, '#': -1, undefined: 1 };`
- `options['*']`
- `options[split[3]]`
- `.match(/\d.?\D/g)`
- `s.match(/(^\d{1,})(S|D|T)(\*|#)?/)`
```javascript
function solution(dartResult) {
    const bonus = { 'S': 1, 'D': 2, 'T': 3 },
          options = { '*': 2, '#': -1, undefined: 1 };

    let darts = dartResult.match(/\d.?\D/g);

    for (let i = 0; i < darts.length; i++) {
        let split = darts[i].match(/(^\d{1,})(S|D|T)(\*|#)?/),
            score = Math.pow(split[1], bonus[split[2]]) * options[split[3]];

        if (split[3] === '*' && darts[i - 1]) darts[i - 1] *= options['*'];

        darts[i] = score;
    }

    return darts.reduce((a, b) => a + b);
}
```
