# [백준]1912 연속합


[https://www.acmicpc.net/problem/1912](http://www.acmicpc.net/problem/1912)

# **풀이:**
1. a[i] 는 i번째를 골랐을 때, 최대값
2. 만약 a[i-1] 이 0 보다 크다면, a[i] += a[i-1]

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;
int a[100001] = { 0 };
int main(void) {
	int n;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> a[i];
	}
	int temp = a[0];
	for (int i = 1; i < n; i++) {
		if(a[i-1] > 0)
			a[i] += a[i - 1];
		temp = max(temp, a[i]);
	}
	cout << temp << endl;
	return 0;
}
```


