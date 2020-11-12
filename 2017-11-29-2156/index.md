# [백준]2156 포도주 시식


https://www.acmicpc.net/problem/2156

# **풀이:**
1. b[i][0] 은 i번째를 골랐을 때, i-1번째를 안고른 경우의 수
2. b[i][1] 은 i번째를 골랐을 때, i-1번째를 고른 경우의 수
3. b[i][2] 은 i번째를 골랐을 때, i-2번째를 안고른 경우의 수

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;

int main(void) {
	int n;
	cin >> n;
	int a[10001];
	for (int i = 0; i < n; i++) {
		cin >> a[i];
	}
	int b[10001][3] = { a[0],a[0],a[0],a[1],a[0] + a[1],a[1],0 };
	int temp;
	for (int i = 2; i < n; i++) {
		for (int t = 0; t < 3; t++) {
			if (t == 0) {
				temp = max(b[i - 2][0], b[i - 2][1]);
				b[i][t] = max(temp, b[i - 2][2]) + a[i];
			}
			if (t == 1)
				b[i][t] = max(b[i - 1][0], b[i - 1][2]) + a[i];
			if (t == 2)
				b[i][t] = b[i - 3][1] + a[i];
		}
	}
	temp = max(b[n - 1][0], b[n - 2][1]);
	temp = max(temp, b[n - 1][1]);
	cout << max(temp, b[n - 1][2]) << endl;
	return 0;
}
```


