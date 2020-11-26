# [백준]2133 타일 채우기


[https://www.acmicpc.net/problem/2133](http://www.acmicpc.net/problem/2133)

# **풀이:**
1. N이 홀수라면 타일을 채울 수 없으므로 언제나 0을 출력한다.
2. 짝수일경우 i를 N/2-1 로 생각하고
3. a[i] = 4 * a[i - 1] - a[i - 2] 로 구한다.

# **코드:**

```c++
#include <iostream>
#include <math.h>
using namespace std;

int main(void) {
	int n;
	long long a[30] = { 3,11,0 };
	cin >> n;
	if (n % 2 == 1)
		cout << "0" << endl;
	else {
		for (int t = 2; t < n/2; t++) {
			a[t] = 4*a[t-1] - a[t-2];
		}
		cout << a[n/2-1] << endl;
	}
	return 0;
}
```


