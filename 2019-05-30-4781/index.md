# [백준]4781 사탕 가게


[https://www.acmicpc.net/problem/4781](http://www.acmicpc.net/problem/4781)

# **풀이:**
1. dp[a]를 a원으로 구매할 수 있는 가장 높은 칼로리라고 한다.
2. 사탕의 칼로리를 s, 가격을 d라고 했을 때, 
3. 현제 a원으로 구매할 수 있는 가장 높은 칼로리와 a-d원 으로 구매할 수 있는 가장높을칼로리 + s 를 비교하여 높은 값으로 교체한다.
3. 즉, dp[t] = max(dp[t], dp[t - d] + s) 를 반복하여 do[m]값을 구한다.

# **코드:**
사용언어 : c++

```C++
#include <iostream>
#include <cstring>
#include <algorithm>
using namespace std;
double M1, d1;
int N, M, s, d, dp[10002];
int main(void) {
	while (1) {
		memset(dp, 0, sizeof(dp));
		cin >> N >> M1;
		if (N == 0)
			break;
		M = M1 * 100;
		for (int i = 0; i < N; i++) {
			cin >> s >> d1;
			d = d1 * 100;
			for (int t = d; t <= M; t++) 
				dp[t] = max(dp[t], dp[t - d] + s);
		}
		cout << dp[M] << endl;
	}
	return 0;
}
```


