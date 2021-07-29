# [백준]13711 LCS 4


https://www.acmicpc.net/problem/13711

# 풀이:

[전기줄 - 2](https://jyukki97.github.io/2568/) 참고



# **코드:** 

사용언어 :  python

```python
import bisect
input()
d,q=dict.fromkeys(map(int,input().split()),0),[]
for k,i in enumerate(map(int,input().split())):d[i]=k
for k,i in d.items():
    s=bisect.bisect_left(q,i)
    if s!=len(q):q[s]=i
    else:q+=[i]
print(len(q))
```

