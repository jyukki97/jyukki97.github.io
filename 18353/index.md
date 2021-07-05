# [백준]18353 병사 배치하기


https://www.acmicpc.net/problem/18353

# 풀이:

[가장 긴 증가하는 부분 수열 5](https://jyukki97.github.io/14003/) 참고

정확히 말하면 가장 긴 감소하는 부분 수열이지 않을까? 라는 생각이 드는 문제이다.

말 그대로 감소하는 것이기에 뒤에서부터 증가하는 수열을 찾을까? 라는 생각이 들었지만, 

귀찮은 관계로 모든 수에 음수 처리를 해주어 가장 긴 증가하는 부분 수열을 찾게되었다.

# **코드:** 

사용언어 :  python

```python
import bisect
n=int(input())
q=[]
for i in map(int,input().split()):
    s=bisect.bisect_left(q,-i)
    if s!=len(q):q[s]=-i
    else:q+=[-i]
print(n-len(q))
```

