# [백준]1003 피보나치 함수

https://www.acmicpc.net/problem/1003

# **풀이:**
1. 0이 쓰이면 카운트 0을 ++
2. 1이 쓰이면 카운트 1을 ++

# **코드:**

```C++
#include <iostream>		// 재귀를 이용
using namespace std;
int cnt[2] = { 0 };
int fibonacci(int n) {
	if (n == 0) {
		cnt[0]++;
		return 0;
	}
	else if (n == 1) {
		cnt[1]++;
		return 1;
	}
	else
		return fibonacci(n-1) + fibonacci(n-2);
}

int main(void) {
	int T,n;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		cnt[0] = 0;
		cnt[1] = 0;
		fibonacci(n);
		cout << cnt[0] << " " << cnt[1] << endl;
	}
	return 0;
}
}
```
```C++
#include <iostream>			// 포문 이용
using namespace std;

int main(void) {
	int T, n;
	int a[41] = { 0 };
	int b[41] = { 0 };
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		a[0] = 1;
		a[1] = 0;
		b[0] = 0;
		b[1] = 1;
		for (int t = 2; t <= n; t++) {
			a[t] = a[t - 1] + a[t - 2];
			b[t] = b[t - 1] + b[t - 2];
		}
		cout << a[n] << " " << b[n] << endl;
	}
}
```

