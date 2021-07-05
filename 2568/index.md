# [백준]2568 전깃줄 - 2


https://www.acmicpc.net/problem/2568

# 풀이:

가장 긴 증가하는 부분수열 문제이다.

B번 전깃줄의 위치를 A번 전깃줄의 위치를 기준으로 정렬한 뒤,  B를 기준으로 가장 긴 증가하는 부분수열을 찾으면 되는 문제이다.

예를들어 예시에서 

|   A   |   1   |   2   |   3   |   4   |   6   |   7   |   9   |   10   |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :----: |
| **B** | **8** | **2** | **9** | **1** | **4** | **6** | **7** | **10** |

위와 같이 정렬된다.

이렇게 정렬 되었을 때, B를 기준으로 가장 긴 증가하는 부분수열은  1, 4, 6, 7, 10 이 되고 남은  8, 2, 9 에 대응되는 A값은 1, 2, 3 3개이다. 

이렇게 계산하면, 예제 값과 다르게 되는데 그 이유는 가장 긴 증가하는 부분수열이 2, 4, 6, 7, 10 으로 하나 더 생길 수 있기 때문이다. 

이 때의 대응되는 A값은 1, 3, 4로 예제의 값과 일치하게 된다.



# **코드:** 

사용언어 :  python

```python
import bisect
q,c,d,e=[],[],[],[]
for _ in range(int(input())):
    i,t=map(int,input().split())
    q.append((i,t))
q.sort()
for _,t in q:
    s=bisect.bisect_left(c,t)
    if len(c)!=s: c[s]=t
    else: c.append(t)
    d.append(s+1)
s=len(c)
print(len(q)-s)
for i in range(len(d)-1,-1,-1):
    if d[i]==s:s-=1
    else:e.append(q[i][0])
for i in e[::-1]:
    print(i)
```

