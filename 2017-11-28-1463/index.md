# [백준]1463 1로 만들기


https://www.acmicpc.net/problem/1463

# **풀이:**
1. i 일때 연산 횟수를 a[i] 라고 둔다.
2. 2와 3으로 동시에 나눠질때, 따로 나눠질때, 나눠지지 않을때로 나눠서 계산한다.
3. n번까지 연산 후 a[n]을 출력한다.

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;
int a[1000002] = { 0 };
int main(void) {
	int n;
	cin >> n;
	for (int i = 2; i <= n; i++) {
		if (i % 2 == 0 && i % 3 == 0) {
			int temp = min(a[i / 2], a[i / 3]);
			a[i] = min(temp, a[i - 1]) + 1;
		}
		else if(i % 2 == 0 && i % 3 != 0)
			a[i] = min(a[i / 2], a[i - 1]) + 1;
		else if(i % 2 != 0 && i % 3 == 0)
			a[i] = min(a[i - 1], a[i / 3]) + 1;
		else
			a[i] = a[i - 1] + 1;
	}
	cout << a[n] << endl;
	return 0;
}
```


