# 1834 나머지와 몫이 같은 수

[https://www.acmicpc.net/problem/1834](http://www.acmicpc.net/problem/1834)

#### **풀이:**
1. 나머지와 몫이 같은 수는 N+1에 배수의 형태로 나타난다.
2. 3일때 4,8 , 4일때 5,10,15 등 n+1의 배수가 n-1번 나타난다.
3. 즉 (n+1)Σ(n-1) 이다.
4. (n+1)n(n-1)/2
5. (n^3-n)/2

#### **코드:**
사용언어 : Python 3
```
n=int(input())
print((n**3-n)//2)
```
