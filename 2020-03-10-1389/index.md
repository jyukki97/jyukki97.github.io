# [백준]1389 케빈 베이컨의 6단계 법칙

https://www.acmicpc.net/problem/1389

# 풀이:

[[C++\]플로이드-와샬 알고리즘(Floyd-Warshall Algorithm)](https://jyukki97.github.io/learn/2020-02-27-floydwarshall/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int N, M, q, w, d[102][102], a, s = 987654321, c, i, t, y;
int main() {
	cin >> N >> M;
	for (i = 0; i < M; i++) {
		cin >> q >> w;
		d[q][w] = 1;
		d[w][q] = 1;
	}
	for (i = 1; i <= N; i++)
		for (t = 1; t <= N; t++)
			if (i != t && !d[i][t])	d[i][t] = 987654321;
	for (i = 1; i <= N; i++)
		for (t = 1; t <= N; t++)
			for (y = 1; y <= N; y++)
				d[t][y] = min(d[t][y], d[t][i] + d[i][y]);
	for (i = 1; i <= N; i++) {
		c = 0;
		for (t = 1; t <= N; t++)	if (i != t)	c += d[i][t];
		if (c < s) {
			s = c;
			a = i;
		}
	}
	cout << a << endl;
}
```

