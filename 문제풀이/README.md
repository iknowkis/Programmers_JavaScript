#### 내장함수
```javascript
.map((e,idx)=>
.reduce((acc,v)=>
.reduceRight()
.filter((v,k) =>

.forEach((e, i, arr) =>

arr.find((e, i) => {
    if(e !== completion[i]){
        return e;
    }
})



delete arr[el]

.unshift()
.shift()
.push()
.pop()
.substring()
.substr()
.replace(/a/ig,'b')
.split('p')
.splice()
.slice()
'str'.repeat()
.match(/p/ig)

arr.indexOf(el)
arr.indexOf('str',len)
arr.includes(el)

'str'.charAt(i) // 특정 위치 문자 반환
char.charCodeAt(0) // char 문자 to 유니코드 리턴
String.fromCharCode(num) // num 유니코드 to 문자

- .fill("*",0,n.length-4)
- .join('')

.sort((a,b)=>a-b)
.reverse()
Array.of(str).map((e,idx)=>
Array(n).keys()


< Object >
{v,k} // {v: PHP, k: 35}
obj['k']

< Set >
new Set
arr.has(el)
arr.delete(el)

Array.from({length: n},(v,index)=>


s1[n].localeCompare(s2[n]) // 인덱스로 정렬
```

```javascript
while (p.length)

new Date()

parseInt
Math.max
Math.min
Math.floor
Math.abs
Math.ceil
Math.sqrt(num) // 제곱근
Math.pow(num,num) // 제곱



[...n]
**num // 제곱
!() // return true or false
eval(code) // 문자열을 코드로 계산

var regex = /^\d{6}$|^\d{4}$/; // 숫자확인 정규식
return regex.test(s);

s.replace(/([a-z])|([A-Z])/g

String(n).length==a?b:solution(n,a+1,b+=String(n)[a]*1) // 재귀
```

#### 구조분해할당
```javascript
const[a,b,c] = command
```
`const [head, ...arr] = row.split(' ') // 구조할당을 통해 배열 헤더 추출`


- `transposer() // 행렬을 바꾸는 메소드 정의`
```javascript
const transpose = matrix =>
    matrix.reduce(
        (result, row) => row.map((_, i) => [...(result[i] || []), row[i]]),
        []
    );
```
