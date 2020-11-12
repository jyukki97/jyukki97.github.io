# [백준]2228 구간 나누기


[https://www.acmicpc.net/problem/2228](http://www.acmicpc.net/problem/2228)

# **풀이:**
1. dp\[n][m] : n개의 숫자를 m개의 구간으로 나눈 최대 합
2. dp\[i][t] = dp\[i - 1][t] : i번째 수를 포함하지 않는 경우
3. dp\[i][t] = max(dp\[i][t], (t == 1 ? 0 : dp\[y - 1][t - 1]) + a[i] - a[y])
	: i번째 수를 포함하는 경우
    i번째를 포함하므로 구간을 하나 빼고 그것에 i번째 수를 포함하는 구간을 더한다.
   
4. max함수를 쓰므로 dp 초기화를 잘해줘야한다.


# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[101] = { 0 }, dp[101][52] = { 0 };
int main(void) {
	int n, m, temp;
	cin >> n >> m;
	fill(dp[0] + 1, dp[0] + m + 1, -2147483646);
	for (int i = 1; i <= n; i++) {
		cin >> temp;
		a[i] = a[i - 1] + temp;
		for (int t = 1; t <= m; t++) {
			dp[i][t] = dp[i - 1][t];
			for (int y = i - 1; y / 2 >= t - 1; y--) {
				dp[i][t] = max(dp[i][t], (t == 1 ? 0 : dp[y - 1][t - 1]) + a[i] - a[y]);
			}
		}
	}
	cout << dp[n][m] << endl;
	return 0;
}
```
