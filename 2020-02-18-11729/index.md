# [백준]11729 하노이 탑 이동 순서

https://www.acmicpc.net/problem/11729

# 풀이:

https://jyukki97.github.io/blog/2020-02-18-towerofhanoi/ 를 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;

void h(int n, int a, int b, int c) {
	if (!n)    return;
	else {
		h(n - 1, a, c, b);
		printf("%d %d\n", a, b);
		h(n - 1, c, b, a);
	}
}

int main() { 
	int n, a = 1;
	cin >> n;
	for (int i = 0; i < n; i++)
		a *= 2;
	cout << a - 1 << endl;
	h(n, 1, 3, 2);
	return 0;
}
```

