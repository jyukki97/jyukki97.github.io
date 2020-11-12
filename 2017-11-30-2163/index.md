# [백준]2163 초콜릿 자르기


[https://www.acmicpc.net/problem/2163](http://www.acmicpc.net/problem/2163)

# **풀이:**
1. N x M 크기의 초콜릿을 자르는 최소의 경우의 수 N * M - 1

# **코드:**

```C++
#include <iostream>
using namespace std;
int main(void) {
	int n, m;
	cin >> n >> m;
	cout << n*m - 1 << endl;
	return 0;
}
```


