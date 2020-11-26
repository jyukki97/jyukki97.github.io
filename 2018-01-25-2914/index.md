# 2914 저작권

[https://www.acmicpc.net/problem/2914](http://www.acmicpc.net/problem/2914)

#### **풀이:**
1. 올림을 했으므로 평균값에서 1을 뺀 후 수록된 곡의 갯수와 곱한 뒤 1을 더해준다.

#### **코드:**
사용언어 : Python 3
```
a, b = map(int, input().split(' '))
print(a * (b-1) + 1)
```
