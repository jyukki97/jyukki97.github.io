# 1789 수들의 합

[https://www.acmicpc.net/problem/1789](http://www.acmicpc.net/problem/1789)

#### **풀이:**
1. 입력받은 숫자를 N 이라고 할 때
2. (-1 + (1+8*N)^0.5)/2 에 소수점을 버린 값이 최대 개수이다.
3. n(n+1)/2 >= k
4. n^2+n-2k >= 0
5. n의 최솟값이다.

#### **코드:**
사용언어 : Python 3
```
print(int((-1+(1+8*int(input()))**.5)/2))
```
