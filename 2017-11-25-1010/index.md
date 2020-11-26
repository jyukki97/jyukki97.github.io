# [백준]1010 다리놓기


https://www.acmicpc.net/problem/1010

# **풀이:**
1. 서쪽 다리(N)에서 동쪽 다리(M)로 연결 이므로 조합인 mCn 을 사용

# **코드:**

```C++
#include <iostream>
using namespace std;

int Comb(int n, int r) {
	if (r == 0 || r == n)
		return 1;
	else if (r == n - 1 || r == 1)
		return n;
	return Comb(n - 1, r) + Comb(n - 1, r - 1);
}

int main(void) {
	int T,n,m;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n >> m;
		cout << Comb(m, n) << endl;
	}
	return 0;
}
```


