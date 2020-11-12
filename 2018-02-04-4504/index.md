# 4504 배수 찾기

[https://www.acmicpc.net/problem/4504](http://www.acmicpc.net/problem/4504)

#### **풀이:**
1. 배수인지 아닌지 확인 후 주어진 조건에 맞게 출력
2. 만약 받아드리는 수가 0이라면 반복을 끝낸다.

#### **코드:**
사용언어 : Python 3
```
n=int(input())
while True:
    k=int(input())
    if k==0:
        break
    if(k%n==0):
        print(k,"is a multiple of %d."%(n))
    else:
        print(k,"is NOT a multiple of %d."%(n))
```
