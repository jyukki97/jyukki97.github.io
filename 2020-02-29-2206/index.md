# [백준]2206 벽 부수고 이동하기

https://www.acmicpc.net/problem/2206

# 풀이:

[[백준\]2178 미로 탐색](https://jyukki97.github.io/blog/2020-02-28-2178/) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <queue>
using namespace std;
int n, m, k = -1, q, w, e, dps;
vector<string> a;
queue<pair<int, pair<int, int>>> dp;
bool b[2][1002][1002];
int main() {
	cin >> n >> m;
	a.resize(n);
	for (int i = 0; i < n; i++)
		cin >> a[i];
	dp.push({ 1, { 0,0 } });
	for (int i = 1; i < n * m + 1; i++) {
		dps = dp.size();
		while (dps--) {
			q = dp.front().first;
			w = dp.front().second.first;
			e = dp.front().second.second;
			if (w == n - 1 && e == m - 1) {
				k = i;
				i = n * m + 1;
				break;
			}
			b[q][w][e] = true;
			if (e + 1 < m && a[w][e + 1] == '0' && !b[q][w][e + 1]) {
				dp.push({ q,{w, e + 1 } });
				b[q][w][e + 1] = true;
			}
			if (w + 1 < n && a[w + 1][e] == '0' && !b[q][w + 1][e]) {
				dp.push({ q,{w + 1, e } });
				b[q][w + 1][e] = true;
			}
			if (w >= 1 && a[w - 1][e] == '0' && !b[q][w - 1][e]) {
				dp.push({ q,{w - 1, e} });
				b[q][w - 1][e] = true;
			}
			if (e >= 1 && a[w][e - 1] == '0' && !b[q][w][e - 1]) {
				dp.push({ q,{w,e - 1 } });
				b[q][w][e - 1] = true;
			}
			if (q) {
				if (e + 1 < m && a[w][e + 1] == '1' && !b[q - 1][w][e + 1]) {
					dp.push({ q - 1,{w, e + 1 } });
					b[q - 1][w][e + 1] = true;
				}
				if (w + 1 < n && a[w + 1][e] == '1' && !b[q - 1][w + 1][e]) {
					dp.push({ q - 1,{w + 1, e } });
					b[q - 1][w + 1][e] = true;
				}
				if (w >= 1 && a[w - 1][e] == '1' && !b[q - 1][w - 1][e]) {
					dp.push({ q - 1,{w - 1, e} });
					b[q - 1][w - 1][e] = true;
				}
				if (e >= 1 && a[w][e - 1] == '1' && !b[q - 1][w][e - 1]) {
					dp.push({ q - 1,{w,e - 1 } });
					b[q - 1][w][e - 1] = true;
				}
			}
			dp.pop();
		}
	}
	cout << k << endl;
}
```

