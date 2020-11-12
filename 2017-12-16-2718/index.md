# [백준]2718 타일 채우기


[https://www.acmicpc.net/problem/2718](http://www.acmicpc.net/problem/2718)

# **풀이:**
1. a[t] 는 4 x t 크기의 타일을 채울 수 있는 경우의 수
2. a[t] = a[t - 1] + a[t - 2] * 5 + a[t - 3] - a[t - 4];

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[30] = { 1,5,11,36 };
int main(void) {
	int T,n,cnt;
	cnt = 5;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		if (a[n - 1] == 0)
			for (int t = cnt-1; t < n; t++) {
				a[t] = a[t - 1] + a[t - 2] * 5 + a[t - 3] - a[t - 4];
			}
		cout << a[n - 1] << endl;
		cnt = max(cnt, n);
	}
	return 0;
}
```


