# [백준]10942 팰린드롬?

https://www.acmicpc.net/problem/10942

# 풀이:

DP\[i][t] : i 번쨰 수 부터 t 번째 까지 수가 팰린드롬을 이룬다면 1, 아니라면 0

a[i] == a[t] 라면,

DP\[i][t] = DP\[i + 1][t - 1] 

a[i] != a[t] 라면,

DP\[i][t] = 0



###### 테스트 케이스가 많아 시간초과가 날 수 있으므로 메모이제이션을 하자!



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string.h>
using namespace std;
int m, n, q, w, a[2002], dp[2002][2002];
int p(int x, int y) {
	if (dp[x][y] != -1) return dp[x][y];
	if (x > y)		dp[x][y] = 1;
	else
		if (a[x] == a[y])	dp[x][y] = p(x + 1, y - 1);
		else	dp[x][y] = 0;
	return dp[x][y];
}
int main() {
	scanf("%d", &n);
	for (int i = 1; i <= n; i++)
		scanf("%d", &a[i]);
	scanf("%d", &m);
	memset(dp, -1, sizeof(dp));
    while (m--) {
		scanf("%d %d", &q, &w);
		printf("%d\n", p(q, w));
	}
}
```

