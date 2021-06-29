# [백준]11000 강의실 배정


https://www.acmicpc.net/problem/11000

# 풀이:

그리디 문제이다.

강의 시간을 시작 시간 기준으로 정렬해 놓는다.

맨 처음 우선순위 큐에 0을 넣어놓는다.

강의 시작 시간이 제일 적은 것부터 우선순위 큐의 맨 앞의 값과 비교한다. 만약, 강의 시작 시간이 큐의 맨 앞의 값보다 크다면, 큐에서 pop해준다.

강의 끝나는 시간을 우선순위 큐에 pop 해준다.

이렇게 되면, 만약, 강의를 연달아 할 수 있다면, 강의실 개수(큐의 크기)는 유지되고, 연달아 할 수 없다면, 강의실 개수는 늘어나게 된다.

마지막으로 강의실 개수를 출력하고 끝낸다.



{{< admonition type=warning title="주의사항" open=false >}}

맨 윗줄에 input = sys.stdin.readline 를 꼭 추가해주자. 시간초과난다.

처음엔 일반적인 시간표 문제처럼 끝나는 시간을 기준으로 정렬했으나, 아니더라 조심하도록 하자.

{{< /admonition >}}

# **코드:** 

사용언어 :  python

```python
import heapq as H
import sys
f=sys.stdin.readline
a,q=[],[0]
for _ in range(int(f())):
    x,y=map(int,f().split())
    a.append((x,y))
a.sort()
for x,y in a:
    if q[0]<=x:H.heappop(q)
    H.heappush(q,y)
print(len(q))
```

