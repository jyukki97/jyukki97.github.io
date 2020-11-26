# [백준]11727 2xN 타일링2


[https://www.acmicpc.net/problem/11727](http://www.acmicpc.net/problem/11727)

# **풀이:**
1. a[i] 는 타일이 2xi 일때의 경우의 수
2. a[i] = (2 * a[i - 2] + a[i - 1]
3. 주어진 조건에서 10007으로 나눈 나머지를 출력하라고 하였으므로 나눠줌.

# **코드:**

```C++
#include <iostream>
using namespace std;
int a[1001] = { 1,3,0 };
int main(void) {
	int n;
	cin >> n;
	for (int i = 2; i < n; i++) {
		a[i] = (2 * a[i - 2] + a[i - 1])%10007;
	}
	cout << a[n - 1] << endl;
	return 0;
}
```


