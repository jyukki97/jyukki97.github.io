# [백준]12738 가장 긴 증가하는 부분 수열 3


https://www.acmicpc.net/problem/12738

# 풀이:

[가장 긴 증가하는 부분 수열 5](https://jyukki97.github.io/14003/) 참고





# **코드:** 

사용언어 :  python

```python
import bisect
input()
q=[]
for i in map(int,input().split()):
    s=bisect.bisect_left(q,i)
    if s!=len(q):q[s]=i
    else:q+=[i]
print(len(q))
```

