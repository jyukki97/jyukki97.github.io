# [백준]17267 상남자


https://www.acmicpc.net/problem/17267

# 풀이:

스타트 지점부터 움직일 수 있는 지점으로 움직인다.



움직일 때, 왼쪽으로 움직였다면 left 값을 -1 해주고,



오른쪽으로 움직였다면 right값을 -1해주면서 움직이자.







주의사항 :

1. 위아래를 한칸씩 움직일 경우 안되는 case가 존재. 움직일 수 있는 한도 내에서 다 움직이자!!.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <vector>
#include <queue>
#include <string.h>
using namespace std;
int w[1005][1005];
int main() {
	int i, t, n, m, l, r, c = 0;
	cin >> n >> m >> l >> r;
	queue<vector<int>> q;
	memset(w, 0, sizeof(w));
	for (i = 0; i < n; i++) {
		for (t = 0; t < m; t++) {
			scanf("%1d", &w[i][t]);
			if (w[i][t] == 2) q.push({ i,t,l,r });
		}
	}
	while (!q.empty()) {
		c++, i = q.front()[0], t = q.front()[1], l = q.front()[2], r = q.front()[3];
		while (++i < n && !w[i][t]) w[i][t] = 1, q.push({ i,t,l,r });
		i = q.front()[0];
		while (--i >= 0 && !w[i][t]) w[i][t] = 1, q.push({ i,t,l,r });
		i = q.front()[0];
		if (t < m - 1 && !w[i][t + 1] && r > 0) w[i][t + 1] = 1, q.push({ i,t + 1,l,r - 1 });
		if (t > 0 && !w[i][t - 1] && l > 0) w[i][t - 1] = 1, q.push({ i,t - 1,l - 1,r });
		q.pop();
	}
	cout << c << endl;
}
```
