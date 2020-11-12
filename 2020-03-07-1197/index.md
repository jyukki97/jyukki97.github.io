# [백준]1197 최소 스패닝 트리

https://www.acmicpc.net/problem/1197

# 풀이:

배열 v를 현재 만들어진 트리에 들어있는 노드들의 집합 이라고 하자.

시작할 때 배열 v에 1 하나만 넣고 시작한다.

배열 v를 모두 순회하여 현재 트리에서 뻗어갈 수 있고, 가중치가 가장 작은 간선을 찾는다.

간선을 연결 한 후 연결된 노드를 배열 v에 저장한다.

배열 v에 모든 정점이 들어올때까지 반복한다.



트리에 모든 가중치를 더해 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
#include <vector>
using namespace std;
typedef pair<int, int> P;
int N, E, q, w, e, b[10002] = { 1,1 };
vector<priority_queue<P, vector<P>, greater<P>>> a;
int main() {
	cin >> N >> E;
	a.resize(N + 1);
	vector<int> v = { 1 };
	for (int i = 0; i < E; i++) {
		cin >> q >> w >> e;
		a[q].push({ e,w });
		a[w].push({ e,q });
	}
	P p;
	q = 0;
	while (1) {
		p = { 1000002, 0 };
		for (int i : v) {
			while (!a[i].empty()) {
				if (b[a[i].top().second])	a[i].pop();
				else if (p.first > a[i].top().first) p = a[i].top();
				else	break;
			}
		}
		if (p.first < 1000001) {
			b[p.second]++;
			v.push_back(p.second);
			q += p.first;
		}
		else	break;
	}
	cout << q << endl;
}
```

