# [백준]2098 외판원 순회


[https://www.acmicpc.net/problem/2098](http://www.acmicpc.net/problem/2098)

# **풀이:**
1. dp\[a][b]를 현제 위치가 a이고, 이때까지 방문한 도시들의 목록이 b인 여행비용의 최솟값이라고 한다.
2. 방문한 도시들을 쉽게 나타내기 위해 비트마스크를 사용하였다.
3. 최솟값을 구하는 문제이므로 r을 최대한 큰 수로 두고 min함수를 이용한다.
4. 도시의 비용이 0인 경우 방문할 수 없으므로 제외시킨다.
5. 방문 횟수가 많아 시간초과가 날 수 있으므로 메모이제이션을 한다.
6. 순회 문제이기 때문에 시작위치는 상관없으므로 실행시간을 늘리지 않도록 주의한다.

# **코드:**
사용언어 : c++

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int w[17][17],d[17][100000], n;
int T(int a, int b) {
	if ((1 << n) - 1 == b && w[a][0] != 0)
		return w[a][0];
	int &r = d[a][b];
	if (r > 0)
		return r;
	r = 100000000;
	for (int i = 0; i < n; i++)
		if (w[a][i] != 0 && (b & (1 << i)) == 0)
			r = min(r, w[a][i] + T(i, b | (1 << i)));
	return r;
}
int main(void) {
	cin >> n;
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			cin >> w[i][t];
	cout << T(0, 1) << endl;
	return 0;
}
```
