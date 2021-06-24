# [백준]1241 머리 톡톡


https://www.acmicpc.net/problem/1241

# 풀이:

1번 부터 N번까지 학생들의 머리 위의 숫자들의 개수를 저장해놓는다

ex) 2는 2번, 1은 1번...

자신의 머리 위의 수를 소인수분해한다.

소인수분해를 통해 나온 약수들이 나온 개수만큼 모두 더해준다.

자기 자신과 같은 수 일 때는 자기 자신을 세지않으므로 조심하자.





# **코드:** 

사용언어 :  python

```python
import math
N=int(input())
a=[]
d=dict()
for i in range(N):
    a.append(int(input()))
    d[a[-1]] = d.get(a[-1], 0) + 1
b=[0] * N
for key, i in enumerate(a):
    for t in range(1, int(math.sqrt(i) + 1)):
        if i % t == 0:
            b[key] += (d.get(t, 0) - (i//t == i) if t != i//t else 0) 
            	+ d.get(i//t, 0) - (t == i)
for i in range(N):
    print(b[i])
```
