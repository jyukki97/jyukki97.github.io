# 1629 곱셈

[https://www.acmicpc.net/problem/1629](http://www.acmicpc.net/problem/1629)

#### **풀이:**
1. a, 19 일 때
2. a*a^18
3. a*(a^9)^2
4. a*(a*(a^4)^2)^2
5. a*(a*((a^2)^2)^2)^2
6. 이런 식으로 풀면 된다.

#### **코드: pow함수 이용**
사용언어 : Python 3
```
a,b,c=map(int,input().split())
print(pow(a,b,c))
```

#### **코드:**
사용언어 : Python 3
```
a,b,c=map(int,input().split())
def q(k):
    if(k==0):return 1
    w=q(k/2)
    n=(w*w)%c
    if(k%2):n=(n*a)%c
    return n
print(q(b))
```
