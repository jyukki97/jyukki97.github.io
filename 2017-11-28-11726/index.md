# [백준]11726 2×n 타일링


https://www.acmicpc.net/problem/11726

# **풀이:**
1. 정수 i를 1,2 의 조합으로 나타낼 수 있는 경우의 수 a[i-1]
2. a[i] = a[i-1] + a[i-2] 으로 구할 수 있다.

# **코드:**

```C++
#include <iostream>
using namespace std;

int main(void) {
	int n;
	int a[1001] = { 1,2,0 };
	cin >> n;
	for (int t = 2; t < n; t++) {
		a[t] = (a[t - 1] + a[t - 2]) % 10007;
	}
		cout << a[n - 1]<< endl;
	return 0;
}
```


