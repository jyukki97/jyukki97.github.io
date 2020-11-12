# [백준]2164 카드2

[https://www.acmicpc.net/problem/2164](http://www.acmicpc.net/problem/2164)

#### **풀이:**
1. 카드의 갯수가 2 ^ i 개일 경우 남게 되는 카드의 번호는 2 ^ i 이다.
2. 카드의 갯수가 (2 ^ i) + n 개  일 경우 남게 되는 카드의 번호는 2 * n 이다.

#### **코드:**
사용언어 : Python 3
```{.python}
n,s=int(input()),1
while s<n:
    s*=2
print(s if s==n else 2*n-s)
```
