# [백준]2225 합분해


[https://www.acmicpc.net/problem/2225](http://www.acmicpc.net/problem/2225)

# **풀이:**
1. a\[i][t] 는 0~i+1 까지 정수 t+1 개를 더하여 그 합이 i+1 이 되는 경우의 수 이다.
2. a\[i][t] = a\[i-1][t] + a\[i][t-1] 로 나타낼 수 있다.
3. 이때 수의 값이 너무 커져 오버플로우가 발생할 수 있으므로 1000000000으로 나눈 나머지를 출력한다.

# **코드:**

```c++
#include <iostream>
using namespace std;
long long a[201][201];
int main(void) {
	int n, k;
	cin >> n >> k;
	for (int i = 0; i < n; i++) {
		a[i][0] = 1;
		for (int t = 1; t < k; t++) {
			if (i == 0)
				a[i][t] = t + 1;
			else
				a[i][t] = ((a[i - 1][t]) % 1000000000 + (a[i][t - 1]) % 1000000000) % 1000000000;
		}
	}
	cout << a[n - 1][k - 1] << endl;
	return 0;
}
```


