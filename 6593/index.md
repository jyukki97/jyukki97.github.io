# [백준]6593 상범 빌딩


https://www.acmicpc.net/problem/6593

# 풀이:

BFS 문제이다.

현재 위치에서 오른쪽, 왼쪽, 위, 아래, 앞, 뒤 6방향을 모두 검사하고 갈 수 있다면, 큐에 집어넣는 방식으로 풀 수 있다.

{{< admonition type=warning title="주의사항" open=false >}}

1. 이미 방문한 위치는 표시하여 다시 방문하지 않게 해주도록 하자.

2. 출력 형식을 주의 깊게 보자. 틀렸습니다의 절반 이상이 이 문제일 가능성이 높다.

   {{< /admonition >}}

처음에 파이썬으로 풀었는데 답 제출에서 IndexOutOfBound가 뜨더라... 분명히 정답이 뜬 c++ 코드와 같은 코드인데 문제를 모르겠다. 

# **코드:** 

사용언어 :  C++

```c++
#include <iostream>
#include <vector>
#include <queue>
#define P pair<pair<int, int>, int>
using namespace std;
int main() {
	while (1) {
		int l,r,c, v[32][32][32] = { 0 }, d = 0, f = 1, x[6] = { 1,-1,0,0,0,0 }, y[6] = { 0,0,1,-1,0,0 }, z[6] = { 0,0,0,0,1,-1 };
		cin >> l >> r >> c;
		if (!l) break;
		char a[32][32][32];
		queue<P> q;
		for (int i = 0;i < l;i++) {
			for (int t = 0;t < r;t++) {
				for (int y = 0;y < c;y++) {
					cin >> a[i][t][y];
					if (a[i][t][y] == 'S') {
						q.push({ {i,t}, y });
						v[i][t][y] = 1;
					}
				}
			}
		}
		for (;f && !q.empty();d++) {
			queue<P> q2;
			while (!q.empty()) {
				P w = q.front();
				q.pop();
				int x1 = w.first.first, y1 = w.first.second, z1 = w.second;
				for (int i = 0;i < 6;i++) {
					int x2 = x1 + x[i], y2 = y1 + y[i], z2 = z1 + z[i];
					if (x2<0 || x2 >= l || y2 < 0 || y2 >= r || z2 < 0 || z2 >= c) continue;
					if (a[x2][y2][z2] != '#' && !v[x2][y2][z2]) {
						if (a[x2][y2][z2] == 'E') {
							f = 0;
							break;
						}
						q2.push({ {x2,y2},z2 });
						v[x2][y2][z2] = 1;
					}
				}
			}
			q = q2;
		}
		if (f)	printf("Trapped!\n");
		else printf("Escaped in %d minute(s).\n", d);
	}
}
```

# **파이썬 코드: 런타임에러뜸** 

사용언어 :  python

```python
while 1:
    l,r,c=map(int,input().split())
    if not l: break
    a,q,v,d=[[input() for _ in range(r)] for _ in range(l)],[],[[[0]*c for _ in range(r)] for _ in range(l)],0
    for i in range(l):
        for t in range(r):
            if a[i][t].find('S')!=-1:
                w=(i,t,a[i][t].find('S'))
    x,y,z=[1,-1,0,0,0,0],[0,0,1,-1,0,0],[0,0,0,0,1,-1]
    q.append(w)
    v[w[0]][w[1]][w[2]]=1
    while 1:
        q2=[]
        while len(q):
            x1,y1,z1=q.pop()
            if a[x1][y1][z1]=='E': break
            for i in range(6):
                x2,y2,z2=x1+x[i],y1+y[i],z1+z[i]
                if 0<=x2<l and 0<=y2<r and 0<=z2<c:
                    if a[x2][y2][z2]!='#' and not v[x2][y2][z2]:
                        q2.append((x2,y2,z2))
                        v[x2][y2][z2]=1
        if not len(q2): break
        q=q2.copy()
        d+=1
    if a[x1][y1][z1]!='E': print("Trapped!")
    else: print("Escaped in %d minute(s)." %(d))
```


