# 1297 TV 크기

[https://www.acmicpc.net/problem/1297](http://www.acmicpc.net/problem/1297)

#### **풀이:**
1. 대각선길이, 높이비율, 너비비율을 각각 a,b,c라고 할 때
2. a^2 = (bx)^2 + (cx)^2  로 나타낼 수 있다.
3. 이때 x 값이 a/((b*b+c*c)^0.5) 로 나타내지고
4. 진짜 길이를 각각 bx, cx로 나타낼 수 있다.

#### **코드:**
사용언어 : Python 3
```
a,b,c=map(int,input().split())
x=a/((b*b+c*c)**.5)
print("%d %d"%(int(b*x),int(c*x)))
```
