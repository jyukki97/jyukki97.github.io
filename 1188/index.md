# [백준]1188 음식 평론가


https://www.acmicpc.net/problem/1188

# 풀이:

소시지가 N개 평론가가 M명 있을 때,

각각의 평론가는 N/M개의 소시지를 가지고 간다. (그러므로 만약, N이 M으로 나누어 떨어진다면 소시지를 자르지 않아도 된다.) => GCD(N, M) = M

N개의 소시지를 이어붙여 1개의 소시지로 만든다면, 소시지는 M - 1번 잘라야 한다. => GCD(N, M) = 1

즉, M - GCD(N, M) 번 자른다면 평론가들은 모두 동일한 양의 소시지를 얻을 수 있다.





# **코드:** 

사용언어 :  python

```python
import math
n,m=map(int,input().split())
print(m-math.gcd(n,m))
```
