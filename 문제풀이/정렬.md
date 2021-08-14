### array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하기
![2](https://user-images.githubusercontent.com/87289383/129449246-2269be8a-e8a4-4168-aa59-e0dae08c18ae.JPG)

#### 풀이)
```javascript
function solution(array, commands) {
    var i;
    var pickFrom;
    var pickTo;
    var selectEl;
    var answer = [];

    for(i=0; i<commands.length; i++) {
        pickFrom = commands[i][0];
        pickTo = commands[i][1];
        selectEl = commands[i][2];
        var v1=[];
        
        while(pickFrom<pickTo+1) {
            v1.push(array[pickFrom-1]);
            v1.sort((a,b)=>a-b);
            
            pickFrom++;
            }
        answer.push(v1[selectEl-1]);
    }
    return answer;
}
```

#### 풀이)
- map
- const[a,b,c] = command // 구조분해할당
- filter
- sort
```javascript
    function solution(array,commands) {
        return commands.map(command => {
            const [a,b,c] = command
            const val = array
                .filter((value,idx)=>idx>=a-1&&idx<=b-1)
                .sort((a,b)=>a-b)
            const answer = val[c-1]
            return answer;
        })
    }
```

#### 풀이)
- map
- slice
```javascript
    function solution(array, commands) {
      return commands.map(v=> {
      return array.slice(v[0]-1,v[1]).sort((a,b)=>a-b).slice(v[2]-1,v[2])[0];
      })
    }
```

#### 풀이)
- map(([i,j,k])=>
- slice
```javascript
    var solution = (a,b) => b.map(([i,j,k])=> a.slice(i-1,j).sort((a,b)=>a-b)[k-1]);
```
