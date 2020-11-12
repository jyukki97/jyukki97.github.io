# [백준]11057 오르막수


[https://www.acmicpc.net/problem/11057](http://www.acmicpc.net/problem/11057)

# **풀이:**
1. a[i][t] 는 길이가 i인 수에서 1의 자리가 t인 수의 오르막 수의 개수
2. a[i][t] += max(a[i - 1][t], a[i][t - 1]);

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;
int a[1002][1002] = { 0 };
int main(void) {
	int n, m;
	cin >> n >> m;
	for (int i = 1; i <= n; i++) {
		for (int t = 1; t <= m; t++) {
			cin >> a[i][t];
		}
	}
	for (int i = 1; i <= n; i++) {
		for (int t = 1; t <= m; t++) {
			a[i][t] += max(a[i - 1][t], a[i][t - 1]);
		}
	}
	cout << a[n][m] << endl;
	return 0;
}
```


