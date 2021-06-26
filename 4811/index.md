# [백준]4811 알약


https://www.acmicpc.net/problem/4811

# 풀이:

카탈란 수 문제이다.

깔끔하게 카탈란 수로 풀어주자.

$${2nCn \over n + 1}$$



# **코드:** 

사용언어 :  python

```python
from math import factorial as f
while a:=int(input()): print(f(2*a)//(f(a)*f(a+1)))
```
