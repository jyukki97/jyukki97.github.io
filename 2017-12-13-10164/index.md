# [백준]10164 격자상의 경로


[https://www.acmicpc.net/problem/10164](http://www.acmicpc.net/problem/10164)

# **풀이:**
1. N X M 행렬에서 K번째 수를 꼭 지나치면서 오른쪽 맨 아래까지 가는 최대 경우의 수
2. 1~K 까지 가는 경우의 수 * K~M*N 까지 가는 경우의 수
3. DP\[i][t] i행 t열로 갈 수 있는 경우의 수
4. DP\[i][t] = DP\[i-1][t] + DP\[i][t-1]

# **코드:**

```C++
#include <iostream>
using namespace std;
int a[16][16] = { 0 };
int b[16][16] = { 0 };
int main(void) {
	int n, m, k, q, w, e, r;
	cin >> n >> m >> k;
	q = k / m + 1;
	w = k%m;
	if (k != 0 && w == 0) {
		w = m;
		q = k / m;
	}
	if (k == 0) {
		q = n;
		w = m;
	}
	e = n - q + 1;
	r = m - w + 1;
	for (int i = 0; i < q; i++) {
		for (int t = 0; t < w; t++) {
			if (i == 0 || t == 0)
				a[i][t] = 1;
			else
				a[i][t] = a[i - 1][t] + a[i][t - 1];
		}
	}
	for (int i = 0; i < e; i++) {
		for (int t = 0; t < r; t++) {
			if (i == 0 || t == 0)
				b[i][t] = 1;
			else
				b[i][t] = b[i - 1][t] + b[i][t - 1];
		}
	}
	cout << b[e - 1][r - 1] * a[q - 1][w - 1] << endl; 
	return 0;
}

```


