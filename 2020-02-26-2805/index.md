# [백준]2805 나무 자르기

https://www.acmicpc.net/problem/2805

# 풀이:

[[백준]1654 랜선 자르기](https://jyukki97.github.io/blog/2020-02-26-1654/) 참고



###### m값이 배열의 값보다 작은데 a[i] - m을 할 경우 -값이 나오므로 주의하자.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
long long n, k, i, a[1000001], sum, m, l = 1, r = 0, c = 0;
int main() {
	cin >> k >> n;
	for (i = 0; i < k; i++) {
		cin >> a[i];
		r = max(r, a[i]);
	}
	while (l <= r) {
		sum = 0;
		m = (r + l) / 2;
		for (i = 0; i < k; i++)
			sum += a[i] < m ? 0 : a[i] - m;
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

