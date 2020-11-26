# [백준]1753 최단 경로

https://www.acmicpc.net/problem/1753

# 풀이:

[[C++\]다익스트라 알고리즘(Dijkstra Algorithm)](https://jyukki97.github.io/learn/2020-02-24-dijkstra/) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int V, E, k, u, v, w, i;
vector<int> d;
priority_queue<pair<int, int>> p;
bool b[20002];
int main() {
	cin >> V >> E >> k;
	vector<vector<pair<int, int>>>a(V + 1);
	for (i = 0; i <= V; i++)
		d.push_back(987654321);
	for (i = 0; i < E; i++) {
		cin >> u >> v >> w;
		a[u].push_back({ v,w });
	}
	d[k] = 0;
	p.push({ 0, k });
	while (!p.empty()) {
		w = p.top().second;
		p.pop();
		if (b[w])	continue;
		b[w] = true;
		for (auto t : a[w]) {
			u = t.first, v = t.second;
			if (d[u] > d[w] + v) {
				d[u] = d[w] + v;
				p.push({ d[u], u });
			}
		}
	}
	for (i = 1; i <= V; i++)
		if (d[i] >= 987654321)	cout << "INF" << endl;
		else		cout << d[i] << endl;
}
```

