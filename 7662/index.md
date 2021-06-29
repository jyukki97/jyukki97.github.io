# [백준]7662 이중 우선순위 큐


https://www.acmicpc.net/problem/7662

# 풀이:

우선순위 큐를 이용한 문제이다.

먼저, 우선순위 큐를 두개를 만든다.

만들어진 두 개의 우선순위 큐는 한 개는 오름차순, 한 개는 내림차순으로 정렬하여 사용한다.

다만 이 때, 하나의  우선순위 큐에서 하나의 변수를 삭제했을 때, 다른 우선순위 큐에서 이 변수가 삭제됬는지를 모르므로, Visit 변수를 두어 이 변수가 삭제됐음을 알 수 있게 해준다.

'D 1' 이 입력되어 최댓값을 삭제해야 하는 경우에는 오름차순에서,

'D -1'이 입력되어 최솟값을 삭제해야 하는 경우에는 내림차순에서 삭제한다. 

이때, 삭제되었음을 visit변수에 나타내준다.

또한, 삭제할 때, 이미 삭제된 변수인지 확인하고, 이미 삭제된 변수라면, 패스하고, 다음 것을 삭제한다. 



{{< admonition type=warning title="주의사항" open=false >}}

만약 파이썬을 사용한다면, 맨 윗줄에 input = sys.stdin.readline 를 꼭 추가해주자. 이것때매 몇시간을 날린지 모르겠는데, 결국 이거였을 때의 빡침은 이루말할 수 없다. 꼭 추가해주길 바란다.

{{< /admonition >}}



# **코드:** 

사용언어 :  python

```python
import heapq
import sys
input = sys.stdin.readline
for _ in range(int(input())):
    q,w,v=[],[],[0]*1000002
    for i in range(int(input())):
        a,b=input().split()
        b=int(b)
        if a=='I':
            heapq.heappush(q,(b,i))
            heapq.heappush(w,(-b,i))
            v[i]=1
        elif b==1:
            while w and not v[w[0][1]]: 
                heapq.heappop(w)
            if w:
                v[w[0][1]]=0
                heapq.heappop(w)
        else:
            while q and not v[q[0][1]]:
                heapq.heappop(q)
            if q:
                v[q[0][1]]=0
                heapq.heappop(q)
    while q and not v[q[0][1]]: heapq.heappop(q)
    while w and not v[w[0][1]]: heapq.heappop(w)
    if q: print("%d %d"%(-heapq.heappop(w)[0],heapq.heappop(q)[0]))
    else: print("EMPTY")
```

