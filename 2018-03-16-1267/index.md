# 1267 핸드폰 요금

[https://www.acmicpc.net/problem/1267](http://www.acmicpc.net/problem/1267)

#### **풀이:**
1. 핸드폰 사용시간을 각각 요금제 시간에 맞게 나눈 몫을 구한다
2. 몫을 요금제에 가격에 곱하고 그 가격을 비교한다.
 

#### **코드:**
사용언어 : Python 3
```
a,c,d=int(input()),0,0
b=list(map(int,input().split()))
for i in range(a):
    c+=b[i]//30+ 1
    d+=b[i]//60+ 1
if(c*10<d*15):
    print("Y %d" % (c*10))
elif(c*10==d*15):
    print("Y M %d" % (c*10))
else:
    print("M %d" % (d*15))
```
