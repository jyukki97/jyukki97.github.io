# [백준]1309 동물원


[https://www.acmicpc.net/problem/1309](http://www.acmicpc.net/problem/1309)

# **풀이:**
1. a[i] 가 2 x i 칸에 채울 수 있는 배치의 최댓값이라 하자.
2. a[i] = 2 * a[i - 1] + a[i - 2] 로 구할 수 있다.

# **코드:**

```c++
#include <iostream>
using namespace std;

int main(void) {
	int n;
	cin >> n;
	int a[100001] = { 3,7,0 };
	for (int i = 2; i < n; i++) {
		a[i] = (2* a[i - 1] + a[i - 2]) % 9901;
	}
	cout << a[n - 1] % 9901 << endl;
	return 0;
}
```


