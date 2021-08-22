### 문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬
- strings는 길이 1 이상, 50이하인 배열입니다.
- strings의 원소는 소문자 알파벳으로 이루어져 있습니다.
- strings의 원소는 길이 1 이상, 100이하인 문자열입니다.
- 모든 strings의 원소의 길이는 n보다 큽니다.
- 인덱스 1의 문자가 같은 문자열이 여럿 일 경우, 사전순으로 앞선 문자열이 앞쪽에 위치합니다.

![image](https://user-images.githubusercontent.com/87289383/130359183-352f3a68-07b3-40fc-963f-6266d263fa73.png)

#### 나의 풀이)
```javascript
let solution = (str,n) => str.map(e => [e[n],e]).sort().map(v => v[1])
```

#### 다른 사람 풀이)
- `s1[n].localeCompare(s2[n])`
```javascript
const solution = (strings, n) => strings.sort((s1, s2) => s1[n] === s2[n] ? s1.localeCompare(s2) : s1[n].localeCompare(s2[n]))
```

#### 다른 사람 풀이)
- `.charCodeAt(n)`
```javascript
const solution = (strings, n) => strings.sort().sort((a, b) => a[n] !== b[n] ? a.charCodeAt(n) - b.charCodeAt(n) : 0,)
```
