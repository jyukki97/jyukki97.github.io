# [백준]1865 웜홀

https://www.acmicpc.net/problem/1865

# 풀이:

[[C++\]벨만-포드 알고리즘(Bellman-Ford Algorithm)](https://jyukki97.github.io/learn/2020-02-25-bellmanford/) 참고



###### 벨만-포드 알고리즘으로 모든 정점을 순환 한 뒤, 음수 사이클이 있는지 판단 후 있다면, "YES" 를 없다면 "NO"를 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int	T, n, m, k, i, d[502], a1, a2, a3;
int main() {
	cin >> T;
	while (T--) {
		bool b = true;
		cin >> n >> m >> k;
		vector<pair<pair<int, int>, int>> a;
		for (i = 0; i < m; i++) {
			cin >> a1 >> a2 >> a3;
			a.push_back({ {a1,a2},a3 });
			a.push_back({ {a2,a1},a3 });
		}
		for (i = 0; i < k; i++) {
			cin >> a1 >> a2 >> a3;
			a.push_back({ {a1,a2},-a3 });
		}
		fill(d, d + n + 1, 987654321);
		for (i = 1; i <= n; i++)
			for (auto t : a)		
				if (d[t.first.second] > d[t.first.first] + t.second) {
					d[t.first.second] = d[t.first.first] + t.second;
					if (i == n)		b = false;
				}
		if (b)	cout << "NO" << endl;
		else	cout << "YES" << endl;
	}
}
```

