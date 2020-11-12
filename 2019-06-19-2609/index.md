# [백준]2609 최대공약수와 최소공배수

[https://www.acmicpc.net/problem/2609](http://www.acmicpc.net/problem/2609)

# **풀이:**
1. 두 수를 입력받는다.
2. 두 수의 최대공약수와 최소공배수를 출력한다.

# **코드:**
사용언어 : Python 3
```python
import math
a,b=map(int,input().split())
c=math.gcd(a,b)
print(c,a//c*b)
```
