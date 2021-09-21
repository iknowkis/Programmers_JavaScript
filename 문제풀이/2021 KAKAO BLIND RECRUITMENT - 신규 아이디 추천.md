![image](https://user-images.githubusercontent.com/87289383/134197631-e4610e0c-b8fe-41fa-ae9c-4759d9242fe7.png)
![image](https://user-images.githubusercontent.com/87289383/134197749-c1eb2f2b-11d7-46f0-8115-2b85a2804987.png)

#### 나의 풀이)
```javascript
function solution(id) {
    let step1 = id.toLowerCase()
    let step2 = step1.replace(/[^0-9a-z\-\_\.]/g,'')
    let step3 = step2.split('').filter((e,i)=> !(e=='.' && e==step2[i+1]))
    let step4_1 = step3[0]=='.' ? step3.slice(1,step3.length) : step3
    let step4_2 = step4_1[step4_1.length-1]=='.' ?
            step4_1.slice(0,step4_1.length-1) : step4_1
    let step5 = step4_2.length==0 ? ['a'] : step4_2
    let step6_1 = step5.length >= 16 ? step5.slice(0,15) : step5
    let step6_2 = step6_1[step6_1.length-1]=='.' ?
            step6_1.slice(0,step6_1.length-1).join('') : step6_1.join('')
    let step7 = step6_2.length <= 2 ?
            step6_2+step6_2[step6_2.length-1].repeat(3-step6_2.length) : step6_2
    return step7
}
```

#### 다른 사람 풀이)
```javascript
function solution(new_id) {
    const answer = new_id
        .toLowerCase() // 1
        .replace(/[^\w-_.]/g, '') // 2
        .replace(/\.+/g, '.') // 3
        .replace(/^\.|\.$/g, '') // 4
        .replace(/^$/, 'a') // 5
        .slice(0, 15).replace(/\.$/, ''); // 6
    const len = answer.length;
    return len > 2 ? answer : answer + answer.charAt(len - 1).repeat(3 - len);
}
```

#### 다른 사람 풀이)
- `str.padEnd(1, 'a')`
```javascript
const solution = (new_id) => {
    const id = new_id
        .toLowerCase()
        .replace(/[^\w\d-_.]/g, '')
        .replace(/\.{2,}/g, '.')
        .replace(/^\.|\.$/g, '')
        .padEnd(1, 'a')
        .slice(0, 15)
        .replace(/^\.|\.$/g, '')        
    return id.padEnd(3, id[id.length-1])
}
```

#### 다른 사람 풀이)
- `.match(/^.{0,14}[^.]/)[0]`
- `.replace(/^(.)$/, "$1$1$1")`
- `.replace(/^(.)(.)$/, "$1$2$2");`
```javascript
const solution = new_id =>
    new_id.toLowerCase()
          .replace(/[^\w-_.]/g, "")
          .replace(/\.+/g, ".")
          .replace(/^\.|\.$/g, "")
          .replace(/^$/, "a")
          .match(/^.{0,14}[^.]/)[0]
          .replace(/^(.)$/, "$1$1$1")
          .replace(/^(.)(.)$/, "$1$2$2");
```
