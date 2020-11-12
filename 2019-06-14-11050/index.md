# [백준]11050 이항 계수 1

[https://www.acmicpc.net/problem/11050](http://www.acmicpc.net/problem/11050)

# **풀이:**
1. n, k 를 입력받고, nCk를 출력한다

# **코드:**
사용언어 : Python 3
```python
n,k=map(int,input().split())
r=1
for i in range(k): r*=(n-i)/(i+1)
print((int)(r))
```
