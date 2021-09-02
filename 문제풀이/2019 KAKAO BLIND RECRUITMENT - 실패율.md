![image](https://user-images.githubusercontent.com/87289383/131884107-799caf8e-2387-4dc9-9245-2ad95b900995.png)
![image](https://user-images.githubusercontent.com/87289383/131884317-eaabec5f-448a-4ee9-ba73-712a8364a1b9.png)

#### 나의 풀이)
```javascript
function solution(N, stages,answer=[],i=1) {
    for(i;i<=N;i++) {
        answer.push([i,stages.filter(e=>i==e).length / stages.filter(e=>i<=e).length])
    }
    return answer.sort((a,b)=>b[1]-a[1]).map(v=>v[0]);
}
```

#### 다른 사람 풀이)
```javascript
function solution(N, stages) {
    let ans = []

    for (let i = 1; i <= N; ++i) {
        let usersReachedCurrentStage   = stages.reduce((acc, curStage) => acc + ((curStage >= i) ? 1 : 0), 0)
        let usersStagnatedCurrentStage = stages.reduce((acc, curStage) => acc + ((curStage == i) ? 1 : 0), 0)
        if (usersReachedCurrentStage === 0) {
            ans.push({ 'stage': i, 'failRate': 0 })
            continue
        }
        ans.push({ 'stage': i, 'failRate': (usersStagnatedCurrentStage / usersReachedCurrentStage) })
    }

    return ans.sort((a, b) => {
        if (a.failRate > b.failRate) return -1
        if (a.failRate < b.failRate) return 1
        return a.stage - b.stage
    }).map(entry => entry.stage)
}
```

#### 다른 사람 풀이)
```javascript
function solution(N, stages) {
    let records = [];
    let i;
    for (i = 0; i<N+1; i++) records.push([0,0,i+1]);
    stages.forEach(num => records[num-1][0]++);
    let ppl=0;
    for (i=0; i<N+1; i++){
        records[i][1] = records[i][0]/(stages.length-ppl);
        ppl+=records[i][0];
    }
    return records.slice(0,N).sort((a,b) => b[1]-a[1]).map(el => el[2]);
}
```
