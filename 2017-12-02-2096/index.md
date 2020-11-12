# [백준]2096 내려가기


[https://www.acmicpc.net/problem/2096](http://www.acmicpc.net/problem/2096)

# **풀이:**
1. b\[i][0] 은 i번째 수를 골랐을 때의 최댓값
2. b\[i][0] 은 i번째 수를 골랐을 때의 최솟값

# **참고: [1149 RGB거리](https://jyukki97.github.io/1149/)**
# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[3],c[3];
int main(void) {
	int n,temp;
	cin >> n;
	int b[2][3] = { 0 };
	for (int i = 0; i < n; i++) {
		cin >> a[0] >> a[1] >> a[2];
		c[0] = b[0][0];
		c[1] = b[0][1];
		c[2] = b[0][2];
		temp = max(c[1], c[0]);
		b[0][0] = a[0] + temp;
		b[0][1] = a[1] + max(temp, c[2]);
		b[0][2] = a[2] + max(c[1], c[2]);
		c[0] = b[1][0];
		c[1] = b[1][1];
		c[2] = b[1][2];
		temp = min(c[1], c[0]);
		b[1][0] = a[0] + temp;
		b[1][1] = a[1] + min(temp, c[2]);
		b[1][2] = a[2] + min(c[1], c[2]);
	}
	temp = max(b[0][1], b[0][0]);
	cout << max(temp, b[0][2]) << " ";
	temp = min(b[1][1], b[1][0]);
	cout << min(temp, b[1][2]) << endl;

	return 0;
}
```


