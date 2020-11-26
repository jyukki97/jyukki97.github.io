# [백준]11657 타임머신

https://www.acmicpc.net/problem/11657

# 풀이:

[[C++\]벨만-포드 알고리즘(Bellman-Ford Algorithm)](https://jyukki97.github.io/learn/2020-02-25-bellmanford/) 참고





# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;
#define INF 987654321
int	n, m, i, d[502], a1, a2, a3;
pair<pair<int, int>, int> a[6002];
int main() {
	cin >> n >> m;
	for (i = 0; i < m; i++)
		cin >> a[i].first.first >> a[i].first.second >> a[i].second;
	fill(d, d + n + 1, INF);
	d[1] = 0;
	for (i = 1; i <= n; i++)
		for (auto t : a)
			if (d[t.first.first] != INF && d[t.first.second] > d[t.first.first] + t.second) {
				d[t.first.second] = d[t.first.first] + t.second;
				if (i == n) {
					cout << -1 << endl;
					return 0;
				}
			}
	for (i = 2; i <= n; i++)
		if (d[i] == INF)	cout << -1 << endl;
		else	cout << d[i] << endl;
}
```

