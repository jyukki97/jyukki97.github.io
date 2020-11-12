# [백준]10826 피보나치 수 4

[https://www.acmicpc.net/problem/10826](http://www.acmicpc.net/problem/10826)

# **풀이:**
1. n을 입력받는다
2. n번째 피보나치 수를 출력한다

# **코드:**
사용언어 : Python 3
```python
s,t=0,1
for i in range(int(input())):
 t,s=s,s+t
print(s)
```
