# [백준]10952 A+B - 5

[https://www.acmicpc.net/problem/10952](http://www.acmicpc.net/problem/10952)

# **풀이:**
1. 반복 횟수를 무한히 한 후 입력받은 두 수의 합을 출력
2. 입력받은 두 수가 0 0 이라면 반복문을 빠져나간다.

# **코드:**
사용언어 : Python 3
```python
while 1:
 a,b=map(int,input().split())
 if a==0:break
 print(a+b)
```
