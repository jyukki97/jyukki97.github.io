# [백준]1495 기타리스트


[https://www.acmicpc.net/problem/1495](http://www.acmicpc.net/problem/1495)

# **풀이:**
1. dp\[a][b]를 a 번째 곡을 연주 할 때, b 볼륨으로 연주 할 수 있는가? 라고 하자.
2. dp\[0][S]는 0 번째 곡을 연주 할 때, S 볼륨으로 연주할 수 있으므로(시작지점) 1을 할당한다.
3. 0번째 곡을 연주할 때, S볼륨으로 연주가 가능하다면, 1번째 곡을 연주할 때, S+s[1] or S-s[1] 볼륨도 연주 가능하다(0<=볼륨<=m 일때)
4. 즉, dp\[i][t + s[i]] = dp\[i - 1][t] or dp\[i][t - s[i]] = dp\[i - 1][t]
5. 마지막에 dp[N]값을 모두 순환하며, 가장 높은 값을 출력하고, 가능한 볼륨이 없다면 -1을 출력한다.

# **코드:**
사용언어 : c++

```c++
#include <iostream>
using namespace std;
int s, N, S, M;
bool d[102][1002];
int main(void) {
	cin >> N >> S >> M;
	d[0][S] = 1;
	for (int i = 1; i <= N; i++) {
		cin >> s;
		for (int t = 0; t <= M; t++)
			if (d[i - 1][t]) {
				if (t >= s)
					d[i][t - s] = 1;
				if (t + s <= M)
					d[i][t + s] = 1;
			}
	}
	s = -1;
	for (int i = 0; i <= M; i++)
		if (d[N][i])
			s = i;
	cout << s << endl;
	return 0;
}
```
