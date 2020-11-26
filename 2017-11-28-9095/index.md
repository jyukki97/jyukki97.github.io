# [백준]9095 1, 2, 3 더하기


https://www.acmicpc.net/problem/9095

# **풀이:**
1. 정수 i를 1,2,3의 조합으로 나타낼 수 있는 경우의 수 a[i-1]
2. a[i] = a[i-1] + a[i-2] + a[i-3] 으로 구할 수 있다.

# **코드:**

```C++
#include <iostream>
using namespace std;

int main(void) {
	int T,n;
	cin >> T;
	for (int i = 0; i < T; i++) {
		int a[11] = { 1,2,4,0 };
		cin >> n;
		for (int t = 3; t < n; t++) {
			a[t] = a[t - 1] + a[t - 2] + a[t - 3];
		}
		cout << a[n - 1] << endl;
	}
	return 0;
}
```


