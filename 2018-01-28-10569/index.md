# 10569 다면체

[https://www.acmicpc.net/problem/10569](http://www.acmicpc.net/problem/10569)

#### **풀이:**
1. 면의수 = 2 - 꼭짓점의 수 + 모서리의 수

#### **코드:**
사용언어 : Python 3
```
t=int(input())
for i in range(t):
    v,e=map(int, input().split())
    print(2-v+e)
```
