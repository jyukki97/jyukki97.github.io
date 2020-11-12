# 11006 남욱의의 닭장

[https://www.acmicpc.net/problem/11006](http://www.acmicpc.net/problem/11006)

#### **풀이:**
1. 다리가 잘린 닭의 수
	: 닭의 수 * 2 - 다리의 수
2. 멀쩡한 닭의 수
	: 닭의 수 - 다리가 잘린 닭의 수

#### **코드:**
사용언어 : Python 3
```
t=int(input())
for i in range(t):
    n,m=map(int,input().split())
    print(m*2-n,m-(m*2-n))
```
