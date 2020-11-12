# [백준]2662 기업 투자


[https://www.acmicpc.net/problem/2662](http://www.acmicpc.net/problem/2662)

# **풀이:**
1. dp\[a][b]를 남은 금액이 a원 일 때, b번째 기업에 투자해서 얻을 수 있는 최대 이익이라고 하자.
2. 첫번째 기업에 0원을 투자하는 것 부터 M번째 기업에 N원을 투자하는 것 까지 반복하여 최대 이익금을 구한다.
3. 최대 이익금일 때 각 기업에 얼마를 투자했는지 구한 후 출력한다.
4. 시간초과가 나기 쉬우므로 메모이제이션을 한다.

# **코드:**
사용언어 : c++

```C++
#include <iostream>
#include <cstring>
using namespace std;
int N, M, s[302][22], dp[302][22], x[302][22];
int q(int a, int c) {
	if (c > M)
		return 0;
	int &m = dp[a][c];
	if (m != -1)
		return m;
	m = 0;
	for (int i = 0; i <= a; i++){
		int n = s[i][c] + q(a - i, c + 1);
		if (m < n) {
			m = n;
			x[a][c] = i;
		}
	}
	return m;
}
int main(void) {
	cin >> N >> M;
	memset(dp, -1, sizeof(dp));
	for (int i = 1; i <= N; i++)
		for (int t = 0; t <= M; t++)
			cin >> s[i][t];
	cout << q(N, 1) << endl;
	for (int i = 1; i <= M; i++) {
		cout << x[N][i] << " ";
		N -= x[N][i];
	}
	cout << endl;
	return 0;
}
```


