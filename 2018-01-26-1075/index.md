# 1075 나누기

[https://www.acmicpc.net/problem/1075](http://www.acmicpc.net/problem/1075)

#### **풀이:**
1. 3자리 이후를 유지한 후 주어진 F로 나누어 지는 최솟값을 구하는 문제
2. 답이 한자리 수일 경우 앞에 0을 붙이는 것을 주의하자.

#### **코드:**
사용언어 : Python 3
```
import math
n = int(input())
f = int(input())
print('%02d' % (((math.ceil(((n//100) * 100) / f) * f) % 100)))
```
