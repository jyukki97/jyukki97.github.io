# [백준]9507 Generations of Tribbles


[https://www.acmicpc.net/problem/9507](http://www.acmicpc.net/problem/9507)

# **풀이:**
1. 문제에 DP가 주어져 있으므로 그대로 하면된다.
2. 다만 큰 수가 나오므로 long long을 써야할 것이다.

# **코드:**

```C++
#include <iostream>
using namespace std;
long long a[70] = {1,1,2,4,0};
int main(void) {
	int T,n;
	int cnt = 4;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		for (int t = cnt; t < n + 1; t++) {
			a[t] = a[t - 1] + a[t - 2] + a[t - 3] + a[t - 4];
		}
		cout << a[n] << endl;
		cnt = n + 1;
	}
	return 0;
}
```

