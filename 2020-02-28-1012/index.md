# [백준]1012 유기농 배추

https://www.acmicpc.net/problem/1012

# 풀이:

[[백준\]2667 단지번호붙이기](https://jyukki97.github.io/blog/2020-02-27-2667/) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string.h>
using namespace std;
int n, T, m, k, q, w, sum, a[52][52];
bool b[52][52];
void num(int x, int y) {
	b[x][y] = true;
	if (x + 1 < n && a[x + 1][y] && !b[x + 1][y])
		num(x + 1, y);
	if (y + 1 < m && a[x][y + 1] && !b[x][y + 1])
		num(x, y + 1);
	if (x - 1 >= 0 && a[x - 1][y] && !b[x - 1][y])
		num(x - 1, y);
	if (y - 1 >= 0 && a[x][y - 1] && !b[x][y - 1])
		num(x, y - 1);
}
int main() {
	cin >> T;
	while (T--) {
		sum = 0;
		memset(a, 0, sizeof(a));
		memset(b, 0, sizeof(b));
		cin >> m >> n >> k;
		while (k--) {
			cin >> q >> w;
			a[w][q] = 1;
		}
		for (int i = 0; i < n; i++)
			for (int t = 0; t < m; t++)
				if (a[i][t] && !b[i][t]) {
					sum++;
					num(i, t);
				}
		cout << sum << endl;
	}
}
```

