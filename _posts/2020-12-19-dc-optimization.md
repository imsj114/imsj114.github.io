---
layout: post
title: Divide and Conquer Optimization
use_math: true
---

주로 DP에서 쓰이는 최적화 기법으로, 점화식이 다음과 같은 특별한 조건을 만족할 때 사용할 수 있는 방법이다.

**Condition 1**. $D(t, i) = \min_{k<i}{D(t-1, k) + C(k, i)}$

**Condition 2**.  $A(t, i) := \arg\min_{k<i}{D(t-1, k) + C(k, i)}$일 때, $A(t, i) \leq A(t, i+1)$

최적화 기법 없이 **Condition 1**의 점화식을 구한다면 $O(KN^2)$의 시간이 걸릴 것이다. 하지만 Divide and Conquer Optimization을 사용해 시간복잡도를 $O(KN\log N)$으로 줄일 수 있다. ($t \leq K$, $i \leq N$)

결국 핵심은 **Condition 2**의 정보를 이용해 탐색의 범위를 줄이는 것이다. 다음과 같은 방법으로 고정된 $t$에 대한 $D(t, i)$를 $O(N \log N)$




<!--stackedit_data:
eyJwcm9wZXJ0aWVzIjoiYXV0aG9yOiBTSU1cbiIsImhpc3Rvcn
kiOlsxNzA0ODA3MCwxMTgxODE5NjcxLC0xMTU0NTE5MjQ3LDcz
ODkyODM0MywtMjUyMTc4OTEzLC0zOTYwODY1MzBdfQ==
-->