# [백준]2178 미로 탐색

https://www.acmicpc.net/problem/2178

# 풀이:

이동횟수가 i 일때, 

이동횟수가 i - 1 인 값들에서 왼쪽, 오른쪽, 위, 아래 중 값이 1이고, 방문한적 없는 곳을 찾아 좌표를 큐에 넣는다.

만약 현재 좌표가 도착위치라면, 이동횟수 i를 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int n, m, k, q, w;
vector<string> a;
queue<pair<int, int>> dp2;
bool b[102][102];
int main() {
	cin >> n >> m;
	a.resize(n);
	for (int i = 0; i < n; i++)
		cin >> a[i];
	dp2.push({ 0,0 });
	for (int i = 1; i < n * m + 1; i++) {
		queue<pair<int, int>> dp1;
		while (!dp2.empty()) {
			q = dp2.front().first;
			w = dp2.front().second;
			if (q == n - 1 && w == m - 1) {
				k = i;
				i = n * m + 1;
				break;
			}
			b[q][w] = true;
			if (w + 1 < m && a[q][w + 1] == '1' && !b[q][w + 1]) {
				dp1.push({ q,w + 1 });
				b[q][w + 1] = true;
			}
			if (q + 1 < n && a[q + 1][w] == '1' && !b[q + 1][w]) {
				dp1.push({ q + 1,w });
				b[q + 1][w] = true;
			}
			if (w >= 1 && a[q][w - 1] == '1' && !b[q][w - 1]) {
				dp1.push({ q,w - 1 });
				b[q][w - 1] = true;
			}
			if (q >= 1 && a[q - 1][w] == '1' && !b[q - 1][w]) {
				dp1.push({ q - 1,w });
				b[q - 1][w] = true;
			}
			dp2.pop();
		}
		dp2 = dp1;
	}
	cout << k << endl;
}
```

