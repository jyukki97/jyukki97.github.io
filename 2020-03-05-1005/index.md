# [백준]1005 ACM Craft

https://www.acmicpc.net/problem/1005

# 풀이:

b[i] : i 건물을 짓는데 드는 최소시간

b[i] = max(b[i 건물을 짓는데 필요한 건물들])

-> 바로 전 단계의 건물 중 건설시간이 오래 걸리는 것을 짓는다면, 그 시간동안 다른 건물은 다 지을 수 있기 떄문에, max값만 생각한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int T, N, K, q, e, w, a[1002], m, n, b[1002];
vector<vector<int>> v;
int A(int x) {
	if (b[x] != -1)	return b[x];
	b[x] = 0;
	for (int i : v[x])
		b[x] = max(b[x], A(i));
	b[x] += a[x];
	return b[x];
}
int main(void) {
	cin >> T;
	while (T--) {
		cin >> N >> K;
		fill(b, b + N + 1, -1);
		v.clear();
		v.resize(N + 1);
		for (int i = 1; i <= N; i++)		cin >> a[i];
		for (int i = 0; i < K; i++) {
			cin >> q >> e;
			v[e].push_back(q);
		}
		cin >> w;
		cout << A(w) << endl;
	}
}
```

