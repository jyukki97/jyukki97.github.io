# [백준]1916 최소비용 구하기

https://www.acmicpc.net/problem/1916

# 풀이:

[[C++\]다익스트라 알고리즘(Dijkstra Algorithm)](https://jyukki97.github.io/learn/2020-02-24-dijkstra/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int n, m, u, d[1002], s, e, c, b[1002];
int main() {
	cin >> n >> m;
	priority_queue<pair<int, int>> p;
	vector<vector<pair<int, int>>> a(n + 1);
	while (m--) {
		cin >> s >> e >> c;
		a[s].push_back({ e,c });
	}
	cin >> s >> e;
	fill(d, d + n + 1, 987654321);
	d[s] = 0;
	p.push({ 0, s });
	while (!p.empty()) {
		s = p.top().second;
		p.pop();
		if (b[s])	continue;
		b[s] = true;
		for (auto t : a[s]) {
			u = t.first, c = t.second;
			if (d[u] > d[s] + c) {
				d[u] = d[s] + c;
				p.push({ -d[u], u });
			}
		}
	}
	cout << d[e] << endl;
}
```

