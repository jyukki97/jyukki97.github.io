# [백준]9461 파도반 수열


[https://www.acmicpc.net/problem/9461](http://www.acmicpc.net/problem/9461)

# **풀이:**
1. a[i] 는 i 번째 수열
2. a[i] = a[i-1] + a[i-5]

# **코드:**

```C++
#include <iostream>
using namespace std;
long long a[101] = { 1,1,1,2,2,0 };
int main(void) {
	int T,n;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		for (int t = 5; t < n; t++) {
			a[t] = a[t - 1] + a[t - 5];
		}
		cout << a[n - 1] << endl;
	}
	return 0;
}
```


