---
layout: post
title: Divide and Conquer Optimization
use_math: true
header-includes:
    - \newcommand{\argmin}{\mathop{\mathrm{argmin}}\limits}
---

주로 DP에서 쓰이는 최적화 기법으로, 점화식이 다음과 같은 특별한 조건을 만족할 때 사용할 수 있는 방법이다.

**Condition 1**. $D(t, i) = \min_{k<i}{D(t-1, k) + C(k, i)}$

**Condition 2**.  $A(t, i) := \argmin{k<i}{D(t-1, k) + C(k, i)}$일 때, $A(t, i) \leq A(t, i+1)$

이 때, 




<!--stackedit_data:
eyJwcm9wZXJ0aWVzIjoiYXV0aG9yOiBTSU1cbiIsImhpc3Rvcn
kiOlstMTk2NTQ3ODA4MywtMTE1NDUxOTI0Nyw3Mzg5MjgzNDMs
LTI1MjE3ODkxMywtMzk2MDg2NTMwXX0=
-->