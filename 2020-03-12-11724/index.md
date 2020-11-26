# [백준]11724 연결 요소의 개수

https://www.acmicpc.net/problem/11724

# 풀이:

방문하지 않은 정점과 연결된 모든 정점을 방문표시하고, 요소의 개수를 +1 해준다.

더이상 방문할 정점이 없을때까지 반복한다. 



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int n, m, i, t, c = 0, b[1002];
vector<vector<int>> a;
void T(int x) {
	if (b[x]) return;
	b[x] = 1;
	for (int o : a[x])	T(o);
}
int main() {
	cin >> n >> m;
	a.resize(n + 1);
	while (m--) {
		cin >> i >> t;
		a[i].push_back(t),a[t].push_back(i);
	}
	for (; n > 0; n--)	if (!b[n])	c++, T(n);
	cout << c << endl;
}
```

