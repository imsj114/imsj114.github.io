---
layout: post
title: Divide and Conquer Optimization
use_math: true
---

주로 DP에서 쓰이는 최적화 기법으로, 점화식이 다음과 같은 특별한 조건을 만족할 때 사용할 수 있는 방법이다.

**Condition 1**. $D(t, i) = \min_{k<i}{D(t-1, k) + C(k, i)}$

**Condition 2**.  $k_{opt}(t, i) := \arg\min_{k<i}{D(t-1, k) + C(k, i)}$일 때, $k_{opt}(t, i) \leq k_{opt}(t, i+1)$

최적화 기법 없이 **Condition 1**의 점화식을 구한다면 $O(KN^2)$의 시간이 걸릴 것이다. 하지만 Divide and Conquer Optimization을 사용해 시간복잡도를 $O(KN\log N)$으로 줄일 수 있다. ($t \leq K$, $i \leq N$)

결국 핵심은 **Condition 2**의 정보를 이용해 탐색의 범위를 줄이는 것이다. 다음과 같은 방법으로 고정된 $t$에 대한 $D(t, i)$를 $O(N \log N)$의 시간 안에 구할 수 있다.

```c
void dp(int t, int s, int e, int l, int r){
    // calculate D[t][s..e] given that l <= k_opt <= r
    if(s>e) return;
    int m = (s+e)>>1;
    D[t][m] = MAX_INT;
    int opt;
    for(int k=l; k<=r && k<m; ++k){
        if(D[t][m] > D[t-1][k] + C[k][m]){
            opt = j;
            D[t][m] = D[t-1][k] + C[k][m];
        }
    }
    dp(t, s, m-1, l, opt);
    dp(t, m+1, e, opt, r);
}
```


<!--stackedit_data:
eyJwcm9wZXJ0aWVzIjoiYXV0aG9yOiBTSU1cbiIsImhpc3Rvcn
kiOlstMTkzNzQyMTY5OSwxMTgxODE5NjcxLC0xMTU0NTE5MjQ3
LDczODkyODM0MywtMjUyMTc4OTEzLC0zOTYwODY1MzBdfQ==
-->