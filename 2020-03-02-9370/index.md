# [백준]9370 미확인 도착지

https://www.acmicpc.net/problem/9370

# 풀이:

[[C++\]다익스트라 알고리즘(Dijkstra Algorithm)](https://jyukki97.github.io/learn/2020-02-24-dijkstra/) 참고



s -> g -> h -> x

s -> h -> g -> x

두 가지 경로가 있는데, 둘 중 하나라도 최단 경로일 경우 x를 배열에 저장한다.

저장된 x를 오름차순으로 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int T, n, m, t, u, v, w, i, s, g, h, v1, v2, a1, c, d[2002];
bool b[2002];
priority_queue<pair<int, int>> p;
priority_queue<int, vector<int>, greater<int>> q;
int main() {
	cin >> T;
	while (T--) {
		cin >> n >> m >> t;
		vector<vector<pair<int, int>>> a(n + 1);
		cin >> s >> g >> h;
		for (i = 0; i < m; i++) {
			cin >> u >> v >> w;
			a[u].push_back({ v,w });
			a[v].push_back({ u,w });
			if ((u == g && v == h) || (u == h && v == g))
				a1 = w;
		}
		fill(d, d + n + 1, 3000000);
		fill(b, b + n + 1, 0);
		d[s] = 0;
		p.push({ 0, s });
		while (!p.empty()) {
			w = p.top().second;
			p.pop();
			if (b[w])	continue;
			b[w] = true;
			for (auto t : a[w]) {
				u = t.first, v = t.second;
				if (d[u] > d[w] + v) {
					d[u] = d[w] + v;
					p.push({ -d[u], u });
				}
			}
		}
		v1 = d[g] + a1;
		v2 = d[h] + a1;
		for (i = 0; i < t; i++) {
			cin >> c;
			fill(d, d + n + 1, 3000000);
			fill(b, b + n + 1, 0);
			d[c] = 0;
			p.push({ 0, c });
			while (!p.empty()) {
				w = p.top().second;
				p.pop();
				if (b[w])	continue;
				b[w] = true;
				for (auto t : a[w]) {
					u = t.first, v = t.second;
					if (d[u] > d[w] + v) {
						d[u] = d[w] + v;
						p.push({ -d[u], u });
					}
				}
			}
			if (v1 + d[h] == d[s] || v2 + d[g] == d[s])
				q.push(c);
		}
		while (!q.empty()) {
			cout << q.top() << " ";
			q.pop();
		}
		cout << endl;
	}
}
```

