![image](https://user-images.githubusercontent.com/87289383/134189462-8de40b8c-4f9b-4309-bc59-0cddd0db042a.png)

#### 나의 풀이)
- `isPrime(n) ? : `
```javascript
function solution(nums) {
    var answer = 0
    nums.map((a,ai)=>nums.map((b,bi)=>nums.map((c,ci)=>
        ai<bi && bi<ci ? (isPrime(a+b+c) ? answer++ : 0) : 0)))
    return answer
}
function isPrime(n) {
    if(n%2==0 || n%3==0) return false
    for(var i=5; i<=n; i++) {
        if(n%i==0) {
            return n/i==1
        }
    }
}
```
