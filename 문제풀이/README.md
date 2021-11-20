#### 내장함수
```javascript
.map((e,idx)=>
.reduce((acc,v)=>
.reduceRight()
.filter((v,k) =>
arr1.filter(v => arr2.includes(v))

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

s.replace(/a/ig,'b')
s.replace(new RegExp(a, 'g'), 'a')
s.replace(/^$/, 'a') // null이라면
s.replace(/^\.|\.$/g, '') // 제일 앞과 제일 끝 체크
s.replace(/^(.)$/, "$1$1$1")replace(/^(.)(.)$/, "$1$2$2"); // 길이가 3이 아니라면 끝자리를 붙이기

s.match(/p/ig)
s.match(/^.{0,14}[^.]/)[0] // 길이가 16이상이면 15까지 자르고 끝이 .라면 제거하기
s.match(/\d.?\D/g) // 숫자와 숫자 사이 구분
s.match(/(^\d{1,})(S|D|T)(\*|#)?/) // 24S* 와 같은 숫자+문자+옵션 잘라서 배열로 출력

.split('p')
.splice()
.slice()
'str'.repeat()

arr.indexOf(el)
arr.indexOf('str',len)
arr.includes(el)

'str'.charAt(i) // 특정 위치 문자 반환
char.charCodeAt(0) // char 문자 to 유니코드 리턴
String.fromCharCode(num) // num 유니코드 to 문자

- .fill("*",0,n.length-4)
- .join('')

.sort((a,b)=>a-b)
.sort(([a, b], [c, d]) => b - d);
.reverse()
Array.of(str).map((e,idx)=>
Array(n).keys()


< Object >
{v,k} // {v: PHP, k: 35}
obj['k']

options = { '*': 2, '#': -1, undefined: 1 };
options['*']
options[split[3]]

< Set >
new Set(arr) // duplicator 제거
[...new Set(arr)]
arr.has(el)
arr.delete(el)

Array.from({length: n},(v,index)=>


s1[n].localeCompare(s2[n]) // 인덱스로 정렬
```

```javascript
.padStart(n,0) // n 길이를 만족하도록 앞의 빈 자리 채우기
str.padEnd(1, 'a')

while (p.length)
while(true) {}

loop:{ if() break loop }

new Date()

parseInt
Math.max
Math.min
Math.floor
Math.abs
Math.ceil((100 - a)/s[i]) // 올림
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
solution(n, x + 1) // 재귀함수
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
