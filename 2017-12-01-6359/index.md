# [백준]6359 만취한 상범


[https://www.acmicpc.net/problem/6359](http://www.acmicpc.net/problem/6359)

# **풀이:**
1. n 개의 방이 있을 때 탈출할 수 있는 사람의 수는 sqrt(n)명이다.

# **코드:**

```c++
#include <iostream>
#include <math.h>
using namespace std;
int main(void) {
	int n,T;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		cout << (int)sqrt(n) << endl;
	}
	return 0;
}
```


