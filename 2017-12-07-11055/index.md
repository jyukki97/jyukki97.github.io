# [백준]11055 가장 큰 증가 부분 수열


[https://www.acmicpc.net/problem/11055](http://www.acmicpc.net/problem/11055)

# **풀이:**
1. 배열의 이전을 돌며 가장 합이 큰 값을 더함

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[1002], maxA[1002];
int main(void) {
	int n;
	cin >> n;
	int maximum = 0;
	for (int i = 0; i < n; i++) {
		cin >> a[i];
		maxA[i] = a[i];
	}
	for (int i = 0; i < n; i++) {
		int temp = 0;
		for (int t = i-1; t >= 0; t--) {
			if (a[t] < a[i]) {
				temp = max(temp, maxA[t]);
			}
		}
		maxA[i] += temp;
		maximum = max(maximum, maxA[i]);
	}
	cout << maximum << endl;
	return 0;
}
```


