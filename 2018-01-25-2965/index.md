# 2965 캥거루 세마리

[https://www.acmicpc.net/problem/2965](http://www.acmicpc.net/problem/2965)

#### **풀이:**
1. A 캥거루와 B 캥거루,C 캥거루와 B 캥거루 사이 거리 중 최댓값에서 1을 뺀 값을 출력

#### **코드:**
사용언어 : Python 3
```
a, b, c= map(int, input().split(' '))
print(max(b - a, c - b) - 1)
```
