# [백준]5214 환승

https://www.acmicpc.net/problem/5214

# 풀이:

s[i] : i 번째 하이퍼 튜브에 연결 되어 있는 모든 역

v[i] : i 번 역이 들어있는 하이퍼 튜브

1부터 bfs를 돌아 N번째 역에 도착할 때 지나온 역의 갯수를 출력한다.





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int n, m, k, i, t, w, d, c[1005], b[100005] = { 1,1 };
int main() {
	cin >> n >> k >> m;
	vector<vector<int>> s(m + 1), v(n + 1); queue<int> q;
	for (q.push(1); i < m; i++)
		for (t = 0; t < k; t++) {
			cin >> w;
			s[i].push_back(w);
			v[w].push_back(i);
		}
	for (i = 0;!q.empty() && !d; i++) {
		queue<int> p;
		while (!q.empty()) {
			w = q.front(), q.pop(), d += w == n;
			for (int a : v[w])
				if (!c[a]) {
					c[a]++;
					for (int e : s[a])
						if (!b[e])
							b[e]++, p.push(e);
				}
		}
		q = p;
	}
	printf("%d", d ? i : -1);
}
```

