# [백준]11568 민균이의 계략


[https://www.acmicpc.net/problem/11568](http://www.acmicpc.net/problem/11568)

# **풀이:**
1. [11053 가장 긴 증가하는 부분 수열](https://jyukki97.github.io/11053/) 의 문제와 같으므로 링크를 참고

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
long long a[1001] = { 0 }, b[1001];
int main(void) {
	long long n, temp;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> a[i];
		b[i] = 1;
	}
	for (int i = 0; i < n; i++) {
		temp = 0;
		for (int t = 0; t <= i; t++) {
			if (a[i] > a[i - t])
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

