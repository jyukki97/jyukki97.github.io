# [백준]3745 오름세


https://www.acmicpc.net/problem/3745

# 풀이:

[가장 긴 증가하는 부분 수열 5](https://jyukki97.github.io/14003/) 참고

파이썬에서 EOF 처리하는 방법을 알게되었다.

C++ 에서는 while문 내부에서 cin이나 scanf의 return 값으로 알 수 있었지만, 파이썬은 안되더라.

그냥 단순하게 try catch 문에서 EOF를 감지해서 EOF 일 때 exit() 하는 방법으로 하는 것 같다. 

다른 의견으로는 그냥 무한루프를 돌리면 알아서 중지되면서 맞았습니다가 떴다고 하는데, 나는 안되서 잘 모르겠다.

# **코드:** 

사용언어 :  python

```python
import bisect
try:
    while input():
        q=[]
        for i in map(int,input().split()):
            s=bisect.bisect_left(q,i)
            if s!=len(q):q[s]=i
            else:q+=[i]
        print(len(q))
except:exit()
```

