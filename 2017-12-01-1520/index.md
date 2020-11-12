# [백준]1520 내리막 길


[https://www.acmicpc.net/problem/1520](http://www.acmicpc.net/problem/1520)

# **풀이:**
1. cnt[i][t] 가 i행 t열을 골랐을 때 최대 경로의 수 이다.
2. 왼쪽 위 부터 차례대로 방문한다.
3. 왼쪽, 오른쪽, 위, 아래 를 모두 검사하여 지금 계단의 지점보다 낮은 지점을 찾는다.
4. 계속 검사하면서 가다가 오른쪽 끝 즉, (n,m) 을 만나면 return 1을 해준다.
5. 시간초과 때문에 재방문을 피하기위해 cnt의 값을 모두 -1로 바꿔놓고 0이상이면 검사를 끝내도록 하였다.

# **코드:**

```c++
#include <iostream>
using namespace std;
int n, m;
int a[501][501];
int cnt[501][501];
int downhill(int q, int w) {
	if (q == n && w == m)
		return 1;
	if (cnt[q][w] >= 0)
		return cnt[q][w];
	cnt[q][w] = 0;
	int x[5] = { 0, 1, 0, -1, 0 };
	int y[5] = { 0, 0, 1, 0, -1 };
	for (int i = 0; i < 5; i++) {
		if (q + x[i] > 0 && q + x[i] <= n && w + y[i] > 0 && w + y[i] <= m && a[q + x[i]][w + y[i]] < a[q][w]) {
			cnt[q][w] += downhill(q + x[i], w + y[i]);
		}
	}
	return cnt[q][w];
}
int main(void) {
	cin >> n >> m;
	for (int i = 1; i <= n; i++) {
		for (int t = 1; t <= m; t++) {
			cin >> a[i][t];
		}
	}
	fill(cnt[0],cnt[500], -1);
	cout << downhill(1,1) << endl;
	return 0;
}
```


