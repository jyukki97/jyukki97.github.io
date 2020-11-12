# [백준]1520 내리막 길

https://www.acmicpc.net/problem/1520

# 풀이:

DP\[i][t] : (1,1) ~ (i, t) 까지 내리막으로 갈 수 있는 경우의 수



현재 값에서 왼쪽, 오른쪽, 위, 아래 값이 각각 현재 값보다 크다면,



DP[현재] += DP[왼쪽, 오른쪽, 위, 아래] 로 구할 수 있다.



###### 시간초과가 날 수 있으므로 메모이제이션을 하자!



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string.h>
using namespace std;
int m, n, a[502][502], dp[502][502];
int r(int x, int y) {
	if (dp[x][y] != -1)	return dp[x][y];
	dp[x][y] = 0;
	if (a[x][y] < a[x - 1][y])
		dp[x][y] += r(x - 1, y);
	if (a[x][y] < a[x + 1][y])
		dp[x][y] += r(x + 1, y);
	if (a[x][y] < a[x][y + 1])
		dp[x][y] += r(x, y + 1);
	if (a[x][y] < a[x][y - 1])
		dp[x][y] += r(x, y - 1);
	return dp[x][y];
}
int main() {
	cin >> m >> n;
	for (int i = 1; i <= m; i++)
		for (int t = 1; t <= n; t++)
			cin >> a[i][t];
	memset(dp, -1, sizeof(dp));
	dp[1][1] = 1;
	cout << r(m, n) << endl;
}

```

