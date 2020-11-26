# [백준]11049 행렬 곱셈 순서

https://www.acmicpc.net/problem/11049

# 풀이:

DP\[i][t] : i ~ t 까지의 행렬을 곱하는데 필요한 곱셈 연산 횟수의 최솟값



dp\[x][y] = min(dp\[x][y], f(x, i) + f(i + 1, y) + a[x] * b[i] * b[y])

x ~ i 까지의 행렬 곱셈 + (i + 1) ~ y 까지의 행렬 곱셈 + 그 둘의 곱셈



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
long long n, a[502], b[502], dp[502][502] = {};
long long f(int x, int y) {
	if (x == y || dp[x][y])	return dp[x][y];
	dp[x][y] = f(x, x) + f(x + 1, y) + a[x] * b[x] * b[y];
	for (int i = x + 1; i < y; i++)
		dp[x][y] = min(dp[x][y], f(x, i) + f(i + 1, y) + a[x] * b[i] * b[y]);
	return dp[x][y];
}
int main() {
	cin >> n;
	for (int i = 1; i <= n; i++)
		cin >> a[i] >> b[i];
	cout << f(1, n) << endl;
}

```

