# [백준]2698 인접한 비트의 개수


[https://www.acmicpc.net/problem/2698](http://www.acmicpc.net/problem/2698)

# **풀이:**
1. a\[n]\[k][0] : 크기가 n이고 인접비트의 수가 k이며, 끝에 비트가 0인 수
2. a\[n]\[k][1] : 크기가 n이고 인접비트의 수가 k이며, 끝에 비트가 1인 수
3. a\[n]\[k][0] = a\[n - 1]\[k][0] + a\[n - 1]\[k][1]
4. a\[n]\[k][1] = a\[n - 1]\[k][0] + a\[n - 1]\[k - 1][1]


# **코드:**

```c++
#include <iostream>
using namespace std;
int a[102][102][2] = { 0 };
int main(void) {
	int T, n, k;
	int cnt = 2;
	cin >> T;
	a[1][0][1] = 1; a[1][0][0] = 1;
	for (int i = 0; i < T; i++) {
		cin >> n >> k;
		for (int t = cnt; t < n + 1; t++) {
			for (int y = 0; y < t; y++) {
				a[t][y][0] = a[t - 1][y][0] + a[t - 1][y][1];
				a[t][y][1] = a[t - 1][y][0] + a[t - 1][y - 1][1];
			}
		}
		cout << a[n][k][0] + a[n][k][1] << endl;
		cnt = n;
	}
	return 0;
}
```

