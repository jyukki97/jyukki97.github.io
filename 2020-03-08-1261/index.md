# [백준]1261 알고스팟

https://www.acmicpc.net/problem/1261

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
int N, M, b[102][102], q, w, e, dp[102][102];
int main() {
	cin >> M >> N;
	fill(dp[0], dp[0] + 10201, 987654321);
	vector<string> v(N);
	priority_queue<pair<int, pair<int, int>>> p;
	p.push({ 0,{0,0} });
	dp[0][0] = 0;
	for (int i = 0; i < N; i++)		cin >> v[i];
	while (!p.empty()) {
		q = p.top().second.first;
		w = p.top().second.second;
		e = p.top().first;
		p.pop();
		if (b[q][w])	continue;
		b[q][w] = 1;
		if (w + 1 < M && dp[q][w + 1] > v[q][w + 1] - '0' - e) {
			dp[q][w + 1] = v[q][w + 1] - '0' - e;
			p.push({ -dp[q][w + 1], { q, w + 1 } });
		}
		if (w > 0 && dp[q][w - 1] > v[q][w - 1] - '0' - e) {
			dp[q][w - 1] = v[q][w - 1] - '0' - e;
			p.push({ -dp[q][w - 1], { q, w - 1 } });
		}
		if (q + 1 < N && dp[q + 1][w] > v[q + 1][w] - '0' - e) {
			dp[q + 1][w] = v[q + 1][w] - '0' - e;
			p.push({ -dp[q + 1][w], { q + 1, w } });
		}
		if (q > 0 && dp[q - 1][w] > v[q - 1][w] - '0' - e) {
			dp[q - 1][w] = v[q - 1][w] - '0' - e;
			p.push({ -dp[q - 1][w], { q - 1, w } });
		}
	}
	cout <<	dp[N - 1][M - 1] << endl;
}
```

