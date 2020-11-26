# [백준]9663 N-Queen

https://www.acmicpc.net/problem/9663

# 풀이:

https://jyukki97.github.io/blog/2020-02-23-nqueen/ 을 참고

# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;

bool visit[16][16];
int n, sum = 0;

bool po(int a, int b) {
	for (int i = 1; i <= a || i <= b; i++) {
		if ((a - i  >= 0 && b - i >= 0 && visit[a - i][b - i]) ||
			(a - i >= 0 && b + i < n && visit[a - i][b + i]) ||
			(a - i >= 0 && visit[a - i][b]))	return false;
	}
	return true;
}

void nq(int a) {
	for (int i = 0; i < n; i++) {
		if (po(a, i)) {
			if (a == n - 1)		sum++;
			else {
				visit[a][i] = true;
				nq(a + 1);
				visit[a][i] = false;
			}
		}
	}
}

int main() {
	cin >> n;
	nq(0);
	cout << sum << endl;
	return 0;
}
```

