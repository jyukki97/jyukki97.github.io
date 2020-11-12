# [백준]11066 파일 합치기

https://www.acmicpc.net/problem/11066

# 풀이:

dp\[i][t] = i 장 부터 t 장까지 수록한 파일을 합쳤을 때, 필요한 최소비용

sum[i] = 1 ~ i 까지의 파일 크기의 합



dp\[i][t] = min(dp\[i][t], dp\[i][i] ~ dp\[i][t - 1] + dp\[i + 1][t] ~ dp\[t][t]) 로 구할 수 있다.

겹치는 숫자들이 있으므로, 

dp를 구할 때 마다, dp\[i][t] += sum[t] - sum[i - 1] 을 해주어야 한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int T, n, a[502], dp[502][502] = {}, sum[502];
int f(int a, int b) {
	if (dp[a][b] != 987654321)	return dp[a][b];
	for (int i = 0; a + i < b; i++)
		dp[a][b] = min(dp[a][b], f(a, a + i) + f(i + a + 1, b));
	if (a != 1 || b != n)
		dp[a][b] += sum[b] - sum[a - 1];
	return dp[a][b];
}
int main() {
	cin >> T;
	while (T--) {
		cin >> n;
		for (int i = 1; i <= n; i++)
			for (int t = 1; t <= n; t++)
				dp[i][t] = 987654321;
		for (int i = 1; i <= n; i++) {
			cin >> a[i];
			dp[i][i] = a[i];
			sum[i] = a[i] + sum[i - 1];
		}
		cout << f(1, n) << endl;
	}
}

```

