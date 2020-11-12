# 9764 서로 다른 자연수의 합

[https://www.acmicpc.net/problem/9764](http://www.acmicpc.net/problem/9764)

#### **풀이:**
1. a[i][t]
	: 정수 i를 나타낼 때, 처음 더하는 수가 t인 경우의 수
2. a[i][t]는 i에서 t만큼 뺀 수에서 t보다 큰 수를 더한 값과 동일하다.
3. 예를들어 5 : 1 + 4 = 2 + 3 = 5 로 나타낼 수 있는데 맨 앞자리를 1을 고를 경우 4의 앞자리가 1보다 큰 경우의 수를 모두 더한값과 같다.
4. 이와 동일하게 2,3,4,5를 모두 할 경우 5의 경우의 수는 3개가 나오게 된다.

#### **주의 사항:**
1. n의 경우의 수를 구할 때 값이 매우 커지므로 100999로 나눈 나머지로 출력한다.
2. n의 경우의 수를 구할 때 a[n][n]값을 1로 설정해주는 것을 잊지말자.

#### **코드:**

```
#include <iostream>
#include <algorithm>
using namespace std;
int a[2010][2010] = { 0 };
int main(void) {
	int T, n;
	int q = 1;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		for (int t = q; t <= n; t++) {
			for (int y = 1; y <= t; y++) {
				for (int u = y + 1; u < t; u++) {
					a[t][y] += a[t - y][u] % 100999;
				}
			}
			a[t][t] = 1;
		}
		int sum = 0;
		for (int t = 1; t <= n; t++) {
			sum = (sum % 100999 + a[n][t] % 100999) % 100999;
		}
		cout << sum << endl;
		q = max(q, n + 1);
	}
	return 0;
}
```
