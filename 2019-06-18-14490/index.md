# [백준]14490 백대열

[https://www.acmicpc.net/problem/14490](http://www.acmicpc.net/problem/14490)

# **풀이:**
1. 두 수를 입력받는다(:을 사이에 두고 주어지므로 주의)
2. 두 수의 최대공약수를 구한다.
3. 두 수를 최대공약수로 나눠서 출력한다(최대한으로 약분은 최대공약수로 나누어주면 가능하다)(이때 :을 사이에 두고 출력한다.)

# **코드:**
사용언어 : Python 3
```python
import math
a,b=map(int,input().split(':'))
c=math.gcd(a,b)
print(a//c,b//c,sep=':')
```

