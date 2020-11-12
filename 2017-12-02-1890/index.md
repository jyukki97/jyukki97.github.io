# [백준]1890 점프


[https://www.acmicpc.net/problem/1890](http://www.acmicpc.net/problem/1890)

# **풀이:**
1. cnt[\[x][y] 는 x열 y행 에서의 최대 경로의 개수
2. 시간초과를 막기위해 if (cnt\[x][y] >= 0) 를 넣어 중복을 피함


# **코드:**

```c++
#include <iostream>
using namespace std;
int n, a[101][101];
long long cnt[101][101];
long long jump(int x, int y) {
	if (x == n - 1 && y == n - 1)
		return 1;
	if (cnt[x][y] >= 0)
		return cnt[x][y];
	cnt[x][y] = 0;
	if (a[x][y] + x < n)
		cnt[x][y] += jump(a[x][y] + x, y);
	if (a[x][y] + y < n)
		cnt[x][y] += jump(x, a[x][y] + y);
	return cnt[x][y];
}
int main(void) {
	cin >> n;
	for (int i = 0; i < n; i++) {
		for (int t = 0; t < n; t++) {
			cin >> a[i][t];
		}
	}
	fill(cnt[0], cnt[100], -1);
	cout << jump(0, 0) << endl;
	return 0;
}
```


