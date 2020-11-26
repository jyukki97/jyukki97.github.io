# 2903 중앙 이동 알고리즘

[https://www.acmicpc.net/problem/2903](http://www.acmicpc.net/problem/2903)

#### **풀이:**
1. N 단계를 진행할 경우
2. ((2^N) +1)^2 만큼 점의 개수가 생긴다.

#### **코드:**
사용언어 : Python 3
```
print(((2**int(input()))+1)**2)
```
