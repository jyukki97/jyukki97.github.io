# 2616 소형기관차

[https://www.acmicpc.net/problem/2616](http://www.acmicpc.net/problem/2616)

#### **풀이:**
1. a[i][t]
	: i 번째 까지의 소형 기관차 들이 t번째 객차까지 끌 수 있는 최대 승객의 수
2. 첫 번째 소형기관차부터 앞으로 m칸만큼 객차칸수를 증가시켜가며 최댓값을 구한다. 만약 앞에 값이 더 크다면 앞에값을 선택한다.
3. 객차의 칸이 겹칠 수 없으므로 이번 소형기관차(a[i][t])보다 m보다 작은 객차수를 가지고 있는 이전의 소형기관차(a[i - 1][t - m])를 이번 소형기관창의 t번째 최대 승객 수에 더해준다. 
5. a[i][t] = max(a[i][t - 1], sum[t] - sum[t - m] + a[i - 1][t - m];

#### **코드:**

```
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, sum[50002] = { 0 }, a[4][50002] = { 0 };
int main(void) {
	cin >> n;
	for (int i = 1; i <= n; i++) {
		cin >> sum[i];
		sum[i] += sum[i - 1];
	}
	cin >> m;
	for (int i = 1; i <= 3; i++) {
		for (int t = i * m; t <= n; t++) {
			a[i][t] = max(a[i][t - 1], sum[t] - sum[t - m] + a[i - 1][t - m]);
		}
	}
	cout << a[3][n] << endl;
	return 0;
}
```

#### **시간 초과 코드:**

```
#include <iostream>
#include <algorithm>
using namespace std;
int a[50001];
int main(void) {
	int n, m;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> a[i];
	}
	cin >> m;
	int num = 0;
	for (int i = 0; i <= n - 3 * m; i++) {
		for (int t = i + m; t <= n - 2 * m; t++) {
			for (int y = t + m; y <= n - m; y++) {
				int cnt = 0;
				for (int q = 0; q < m; q++) {
					cnt += a[i + q] + a[t + q] + a[y + q];
				}
				num = max(num, cnt);
			}
		}
	}
	cout << num << endl;
	return 0;
}
```

#### **메모리 초과 코드:**

```
#include <iostream>
#include <algorithm>
using namespace std;
int n, m;
int sum[50002] = { 0 };
int small(int a,int b,int c) {
	if (a + 3 * m > n) return 0;
	if (b + 2 * m > n) return small(a + 1, a + m + 1, a + 2 * m + 1);
	if (c + m > n)	return small(a, b + 1, b + m + 1);
	int num = 0;
	num += sum[a + m] - sum[a] + sum[b + m] - sum[b] + sum[c + m] - sum[c];
	return num = max(num, small(a, b, c + 1));
}
int main(void) {
	cin >> n;
	for (int i = 1; i <= n; i++) {
		cin >> sum[i];
		sum[i] += sum[i - 1];
	}
	cin >> m;
	cout << small(0, m, 2 * m) << endl;
	return 0;
}
```
