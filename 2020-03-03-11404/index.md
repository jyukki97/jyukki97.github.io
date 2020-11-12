# [백준]11404 웜홀

https://www.acmicpc.net/problem/11404

# 풀이:

[[C++\]플로이드-와샬 알고리즘(Bellman-Ford Algorithm)](https://jyukki97.github.io/learn/2020-02-27-floydwarshall/) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int	n, m, i, a1, a2, a3, a[102][102];
int main() {
	cin >> n >> m;
	fill(a[0], a[0] + 10404, 987654321);
	for (i = 0; i < m; i++) {
		cin >> a1 >> a2 >> a3;
		a[a1][a2] = min(a[a1][a2], a3);
	}
	for (i = 1; i <= n; i++) 
		for (int t = 1; t <= n; t++)
			for (int y = 1; y <= n; y++)
				if (t == y) a[t][y] = 0;
				else	a[t][y] = min(a[t][y], a[t][i] + a[i][y]);
	for (i = 1; i <= n; i++) {
		for (int t = 1; t <= n; t++)
			if (a[i][t] == 987654321)	cout << "0 ";
			else	cout << a[i][t] << " ";
		cout << endl;
	}
}
```

