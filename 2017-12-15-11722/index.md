# [백준]11722 가장 긴 감소하는 부분 수열


[https://www.acmicpc.net/problem/11722](http://www.acmicpc.net/problem/11722)

# **풀이:**
1. [11053 가장 긴 증가하는 부분 수열](https://jyukki97.github.io/1965/)의 문제와 똑같으므로 링크를 참고

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int main(void) {
	int n, temp;
	cin >> n;
	int a[1001] = { 0 };
	int b[1001];
	for (int i = 0; i < n; i++) {
		cin >> a[i];
		b[i] = 1;
	}
	for (int i = 0; i < n; i++) {
		temp = 0;
		for (int t = 0; t <= i; t++) {
			if (a[i] < a[i - t])
				temp = max(b[i - t], temp);
		}
		b[i] += temp;
	}
	for (int i = 0; i < n; i++) {
		temp = max(b[i], temp);
	}
	cout << temp << endl;
	return 0;
}
```

