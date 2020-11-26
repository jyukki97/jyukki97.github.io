# [백준]11052 붕어빵 판매하기


https://www.acmicpc.net/problem/11052

# **풀이:**
1. 붕어의 개수가 i개 일 때를 b[i] 라고 놓고
2. b[i] = (t개 일때 가격 + 남은 붕어 빵의 가격) 과 b[i] 개중 큰값을 넣음.
3. 구하고자 하는 n개 즉 b[n]을 찾음. 

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;

int main(void) {
	int n, m, w;
	int a[1002];
	int b[1002] = { 0 };
	cin >> n;
	for (int i = 1; i <= n; i++) {
		cin >> a[i];
	}
	for (int i = 1; i <= n; i++) {
		for (int t = 0; t < i; t++) {
			b[i] = max(b[i], b[t] + a[i - t]);
		}
	}
	cout << b[n] << endl;
	return 0;
}
```


