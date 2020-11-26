# 1398 동전 문제

[https://www.acmicpc.net/problem/1398](http://www.acmicpc.net/problem/1398)

#### **풀이:**
1. a[i]
	: i원의 가격의 차를 사기위한 동전 개수의 최솟값
2. 동전의 크기가 1, 10 25, 100, 1000, 2500 ....
3. 즉, 1, 10, 25가 100단위로 바뀌고있다.
4. 이를 토대로 뒤의 2자리만 계산하여 구한다.
5. cnt += a[n % 100] 10에 자리까지의 동전 개수를 구한 후
6. n을 100으로 나누고 계속 10에 자리까지의 동전 개수를 구한다.
    

#### **코드:**

```
#include <iostream>
#include <algorithm>
using namespace std;
int a[101] = { 0 }, b[3] = { 1,10,25 };
int main(void) {
	int T;
	cin >> T;
	for (int t = 1; t < 100; t++) {
		a[t] = INT32_MAX;
		for (int y = 0; y < 3; y++) {
			if (t - b[y] >= 0) a[t] = min(a[t], a[t - b[y]] + 1);
		}
	}
	for (int i = 0; i < T; i++) {
		long long n;
		int cnt = 0;
		cin >> n;
		while (n > 0) {
			cnt += a[n % 100];
			n /= 100;
		}
		cout << cnt << endl;
	}
	return 0;
}
```
