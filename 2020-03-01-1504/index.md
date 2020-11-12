# [백준]1504 최단 경로

https://www.acmicpc.net/problem/1504

# 풀이:

[[C++\]다익스트라 알고리즘(Dijkstra Algorithm)](https://jyukki97.github.io/learn/2020-02-24-dijkstra/) 참고



지나야 하는 두 개의 정점을 v1, v2 라고 할때,



1 ~ v1 ~ v2 ~ N

1 ~ v2 ~ v1 ~ N

으로 나눠서 풀어본다.



1~v1, v2 과 v1 ~ v2 과 v1, v2 ~ N 을 다익스트라 알고리즘으로 각각 구하여 더한값이

최소인 값을 구한다. 만약 경로가 없다면 -1을 출력한다.

 



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int V, E, u, v, w, i, d[805], v1, v2, a1, a2;
priority_queue<pair<int, int>> p;
bool b[805];
int main() {
	cin >> V >> E;
	vector<vector<pair<int, int>>>a(V + 1);
	for (i = 0; i < E; i++) {
		cin >> u >> v >> w;
		a[u].push_back({ v,w });
		a[v].push_back({ u,w });
	}
	cin >> v1 >> v2;
	fill(d, d + V + 1, 8000000);
	d[1] = 0;
	p.push({ 0, 1 });
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
	a1 = d[v1];
	a2 = d[v2];
	fill(d, d + V + 1, 8000000);
	fill(b, b + V + 1, 0);
	d[v1] = 0;
	p.push({ 0, v1 });
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
	a1 += d[v2];
	a2 += d[v2];
	fill(d, d + V + 1, 8000000);
	fill(b, b + V + 1, 0);
	d[V] = 0;
	p.push({ 0, V });
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
	a1 += d[v2];
	a2 += d[v1];
	a1 = a1 > a2 ? a2 : a1;
	if (a1 >= 8000000)	cout << -1 << endl;
	else	cout << a1 << endl;
}
```

