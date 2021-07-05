# [백준]11003 최솟값 찾기


https://www.acmicpc.net/problem/11003

# 풀이:

dequeue를 사용하는 문제이다.

간단하게 풀 수 있다.

0 번째 숫자부터 N번째 숫자까지 진행한다.

현재 위치가 i일 때, 큐에 마지막에 들어있는 값이 현재 위치의 값보다 크다면, pop한다. 이 것을 현재 위치의 값이 더 클 때까지 반복한다.

즉, 큐의 마지막 값이 현재 값보다 작은 값이 나올때까지 반복하게 된다.

큐의 마지막 값이 현재 값보다 작거나, 큐가 비어있다면, 큐에 마지막에 현재 값을 push해준다.

맨 앞이 가장 작은 값이기에 맨 앞의 값을 출력해줄 것이나, 맨 앞에 값이 i-L+1 ~ i 사이에 오는 값인지 확인하는 작업이 필요하다.

여기서 dequeue가 필요한 이유이다. 맨 앞에 값이 i-L+1 ~ i 사이에 올 때까지 맨 앞의 값을 pop해준다.

맨 앞의 값이 i-L+1 ~ i 사이에 들어온다면 맨 앞의 값을 출력해준다.



{{< admonition type=warning title="주의사항" open=false >}}

처음 문제를 풀 때에는 우선순위 큐가 적혀있길레 heap으로 풀어보려 했지만, 시간초과 나길래 결국 dequeue를 사용하고 말았다.

나처럼 heap을 사용하여 괜한 시간 버리는 일 없도록 하자!!

{{< /admonition >}}

# **코드:** 

사용언어 :  python

```python
from collections import deque
import sys
f=sys.stdin.readline
n,l=map(int,f().split())
a=list(map(int,f().split()))
q=deque()
for i in range(n):
    while q and q[-1][0]>a[i]: q.pop()
    q.append((a[i],i))
    while q[0][1]<=i-l: q.popleft()
    print(q[0][0], end=' ')
```

