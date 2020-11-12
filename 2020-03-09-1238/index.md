# [백준]1238 파티

https://www.acmicpc.net/problem/1238

# 풀이:

[[C++\]다익스트라 알고리즘(Dijkstra Algorithm)](https://jyukki97.github.io/learn/2020-02-24-dijkstra/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
#include <algorithm>
using namespace std;
int V, E, k, u, v, w, i, t, d1[1002], d2[1002], b[1002], s = 0;
int main() {
	cin >> V >> E >> k;
	priority_queue<pair<int, int>> p;
	vector<vector<pair<int, int>>>a(V + 1);
	for (i = 0; i < E; i++) {
		cin >> u >> v >> w;
		a[u].push_back({ v,w });
	}
	fill(d2, d2 + V + 1, 987654321);
	d2[k] = 0;
	p.push({ 0, k });
	while (!p.empty()) {
		w = p.top().second;
		p.pop();
		if (b[w])	continue;
		b[w] = 1;
		for (auto t : a[w]) {
			u = t.first, v = t.second;
			if (d2[u] > d2[w] + v) {
				d2[u] = d2[w] + v;
				p.push({ -d2[u], u });
			}
		}
	}
	for (i = 1; i <= V; i++) {
		if (i == k)	continue;
		fill(d1, d1 + V + 1, 987654321);
		fill(b, b + V + 1, 0);
		d1[i] = 0;
		p.push({ 0, i });
		while (!p.empty()) {
			w = p.top().second;
			p.pop();
			if (b[w])	continue;
			b[w] = 1;
			for (auto t : a[w]) {
				u = t.first, v = t.second;
				if (d1[u] > d1[w] + v) {
					d1[u] = d1[w] + v;
					p.push({ -d1[u], u });
				}
			}
		}
		s = max(s, d1[k] + d2[i]);
	}
	cout << s << endl;
}
```

