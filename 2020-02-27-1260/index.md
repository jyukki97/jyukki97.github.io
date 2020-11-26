# [백준]1260 DFS와 BFS

https://www.acmicpc.net/problem/1260

# 풀이:

DFS 와 BFS를 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <queue>
#include <string.h>
using namespace std;
int n, m, v, q, w, a[1002][1002] = {};
bool b[1002];
void dfs(int x) {
	b[x] = true;
	cout << x << " ";
	for (int i = 1; i <= n; i++)
		if (a[x][i] && !b[i])	dfs(i);
}
int main() {
	cin >> n >> m >> v;
	for (int i = 0; i < m; i++) {
		cin >> q >> w;
		a[q][w] = 1;
		a[w][q] = 1;
	}
	dfs(v);
	cout << endl;
	memset(b, 0, n + 1);
	queue<int> c;
	c.push(v);
	b[v] = true;
	while (!c.empty()) {
		cout << c.front() << " ";
		for (int i = 1; i <= n; i++)
			if (a[c.front()][i] && !b[i]) {
				c.push(i);
				b[i] = true;
			}
		c.pop();
	}
	cout << endl;
}
```

