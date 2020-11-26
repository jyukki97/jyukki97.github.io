# 1668 트로피 진열

[https://www.acmicpc.net/problem/1668](http://www.acmicpc.net/problem/1668)

#### **풀이:**
1. 왼쪽에서부터 높이를 세며, 더 높은 트로피가 나올때마다 카운트를 증가
2. 오른쪽도 똑같이 한 후 카운트를 출력

#### **코드:**
사용언어 : Python 3
```
n,cnt1,cnt2,k1,k2=int(input()),0,0,0,0
h={}
for i in range(n):
    h[i]=int(input())
for i in range(0,n):
    if(h[i]>k1):
        k1=h[i]
        cnt1+=1
    if(h[n-1-i]>k2):
        k2=h[n-1-i]
        cnt2+=1
print(cnt1)
print(cnt2)
```
