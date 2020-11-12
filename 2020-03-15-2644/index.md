# [백준]2644 촌수계산

https://www.acmicpc.net/problem/2644

# 풀이:

[[C++\]다익스트라 알고리즘(Dijkstra Algorithm)](https://jyukki97.github.io/learn/2020-02-24-dijkstra/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
#include <vector>
using namespace std;
int n, k, e, q, w, m, d[102], b[102];
int main() {
	cin >> n >> k >> e >> m;
	vector<vector<int>> a(n + 1);
	priority_queue<pair<int, int>> p;
	while(m--) {
		cin >> q >> w;
		a[q].push_back(w), a[w].push_back(q);
	}
	fill(d, d + n + 1, 101);
	d[k] = 0;
	p.push({ 0, k });
	while (!p.empty()) {
		w = p.top().second;
		p.pop();
		if (b[w])	continue;
		b[w] = true;
		for (auto t : a[w]) {
			if (d[t] > d[w] + 1) {
				d[t] = d[w] + 1;
				p.push({ -d[t], t });
			}
		}
	}
	if (d[e] == 101)	d[e] = -1;
	cout << d[e] << endl;
}
```

