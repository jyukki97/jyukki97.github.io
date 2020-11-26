# 9546 3000번 버스

[https://www.acmicpc.net/problem/9546](http://www.acmicpc.net/problem/9546)

#### **풀이:**
1. 처음 사람의 수 = 2^k - 1

#### **코드:**
사용언어 : Python 3
```
t=int(input())
for i in range(t):
    k=int(input())
    print((2**k)-1)
```
