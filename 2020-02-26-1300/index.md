# [백준]k번째 수

https://www.acmicpc.net/problem/1300

# 풀이:

[[백준]1654 랜선 자르기](https://jyukki97.github.io/blog/2020-02-26-1654/) 참고



현재 숫자의 순서가 k를 넘어간다면,

오른쪽 탐색을, 아니라면 왼쪽으로 탐색한다.



###### int형 사이즈를 넘어가니 long long으로 바꿔주자.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
long long n, k, i, sum, m, l = 1, r, c;
int main() {
	cin >> n >> k;
	r = n * n;
	c = r;
	while (l <= r) {
		sum = 0;
		m = (r + l) / 2;
		for (i = 1; i <= n; i++)
			sum += min(n, m / i);
		if (sum < k)	l = m + 1;
		else {
			c = min(c, m);
			r = m - 1;
		}
	}
	cout << c << '\n';
}

```

