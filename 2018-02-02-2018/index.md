# 2018 수들의 합5

[https://www.acmicpc.net/problem/2018](http://www.acmicpc.net/problem/2018)

#### **풀이:**
1. (i + 1) + (i + 2) + (i + 3) + ... + (i + j) = n
2. i * j + (1 + 2 + 3 + ... + j) = n
3. n - (1 + 2 + 3 + ... + j) = i * j
4. n - j*(j+1)/2 = i * j
5. (n - j*(j+1)/2) / j = i
6. 즉 (n - j*(j+1)/2) / j 가 정수
7. (n - j*(j+1)/2) % j == 0

#### **코드:**
사용언어 : Python 3
```
n,cnt=int(input()),0
for i in range(1,n+1):
    if(n-(i*(i+1))/2 < 0):
        break
    if((n-(i*(i+1))/2)%i==0):
        cnt+=1
print(cnt)
```
