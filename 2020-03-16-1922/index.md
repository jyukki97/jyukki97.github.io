# [백준]1922 네트워크 연결

https://www.acmicpc.net/problem/1922

# 풀이:

[[백준\]1197 최소 스패닝 트리](https://jyukki97.github.io/blog/2020-03-07-1197/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
#include <vector>
using namespace std;
typedef pair<int, int> P;
int N, E, q, w, e, b[1002] = { 1,1 };
int main() {
	cin >> N >> E;
	vector<priority_queue<P, vector<P>, greater<P>>> a(N + 1);
    vector<int> v = { 1 };
	for (int i = 0; i < E; i++) {
		cin >> q >> w >> e;
		a[q].push({ e,w });
		a[w].push({ e,q });
	}
	P p;
	q = 0;
	while (1) {
		p = { 10002, 0 };
		for (int i : v)
			while (!a[i].empty())
				if (b[a[i].top().second])	a[i].pop();
				else if (p.first > a[i].top().first) p = a[i].top();
				else	break;
		if (p.first < 10002) {
			b[p.second]++;
			v.push_back(p.second);
			q += p.first;
		}
		else	break;
	}
	cout << q << endl;
}
```

