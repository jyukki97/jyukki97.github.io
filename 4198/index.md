# [백준]4198 열차정렬


https://www.acmicpc.net/problem/4198

# 풀이:

가장 긴 증가하는 부분수열 문제와 비슷하게 풀 수 있다.

[가장 긴 증가하는 부분 수열 5](https://jyukki97.github.io/14003/) 참고

1 ~ N 까지의 모든 차량을 살펴보면서 진행한다.

현재 차량이 i 일 때, i번째 차량을 기준으로 생각한다.

i+1 ~ N 까지의 차량 중 i 번째 차량을 시작점으로 가장 긴 증가하는 부분수열의 길이를 구하고, 반대로 가장 긴 감소하는 부분수열의 길이를 구한다.

두 부분수열의 길이를 합한 값 중 가장 큰 값을 찾는다.



# **코드:** 

사용언어 :  python

```python
import bisect
def A(f,a):
    q=bisect.bisect_left(f,a)
    if q:
        if len(f)!=q: f[q]=a
        else: f.append(a)
a,m=[int(input())for _ in range(int(input()))],0
for i in range(len(a)):
    c,d=[a[i]],[-a[i]]
    for t in range(i+1, len(a)):
        A(c,a[t])
        A(d,-a[t])
    m=max(m,len(c)+len(d)-1)
print(m)
```

