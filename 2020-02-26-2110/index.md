# [백준]2110 공유기 설치

https://www.acmicpc.net/problem/2110

# 풀이:

[[백준]1654 랜선 자르기](https://jyukki97.github.io/blog/2020-02-26-1654/) 참고



최대 거리를 설정하고,

그 거리를 기준으로 공유기를 설치할 수 있는지 확인하고,

이분탐색으로 최대 거리를 조절해 나간다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
long long n, k, i, a[200001], sum, m, l = 1, r, c = 0, d;
int main() {
	cin >> k >> n;
	for (i = 0; i < k; i++)
		cin >> a[i];
	sort(a, a + k);
	r = a[k - 1];
	while (l <= r) {
		sum = 1;
		m = (r + l) / 2;
		d = a[0];
		for (i = 1; i < k; i++)
			if (d + m <= a[i]) {
				d = a[i];
				sum++;
			}
		if (sum < n)	r = m - 1;
		else {
			c = max(c, m);
			l = m + 1;
		}
	}
	cout << c << endl;
	return 0;
}

```

