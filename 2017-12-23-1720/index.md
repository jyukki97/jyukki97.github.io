# 1720 타일 코드

[https://www.acmicpc.net/problem/1720](http://www.acmicpc.net/problem/1720)

#### **풀이:**
1. a[i] : 2Xi인 타일을 채울 수 있는 경우의 수(중복 포함)
2. b[i] : 2Xi인 타일을 채울 수 있는 경우의 수(중복 미포함)
3. 짝수 일때와 홀수일때 대칭의 경우의 수가 다르므로 나눠서 계산한다.

#### **코드:**

```
#include <iostream>
using namespace std;
int a[32] = { 1,1,3 };
int b[32] = { 1,1,3 };
int main(void) {
	int n;
	cin >> n;
	for (int i = 3; i <= n; i++) {
		a[i] = a[i - 1] + a[i - 2] * 2;
		b[i] = a[i];
	}
	int t = 0;
	if (n % 2 == 1) {
		while (n - t >= 2 && t < n / 2 + 1) {
			b[n] -= a[n - t - 2];
			t++;
		}
	}
	else {
		while (n - t >= 2 && t + 1 < n / 2) {
			b[n] -= a[n - t - 2];
			t++;
		}
	}
	cout << b[n] << endl;
	return 0;
}
```
