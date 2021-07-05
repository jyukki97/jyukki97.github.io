# [백준]2550 전구


https://www.acmicpc.net/problem/2550

# 풀이:

[전기줄 - 2](https://jyukki97.github.io/2568/) 참고



# **코드:** 

사용언어 :  python

```python
import bisect
d,q,c,e={},[],[],[]
n=int(input())
for i in map(int,input().split()):
    d[i]=0
for k,i in enumerate(map(int,input().split())):
    d[i]=k
for k,i in d.items():
    s=bisect.bisect_left(q,i)
    if s!=len(q):q[s]=i
    else:q+=[i]
    c+=[s]
s=len(q)
print(s)
for i in range(n-1,-1,-1):
    if c[i]==s-1:e+=[list(d)[i]];s-=1
print(' '.join(map(str,sorted(e))))
```

