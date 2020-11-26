# [백준]1780 종이의 개수

https://www.acmicpc.net/problem/1780

# 풀이:

[[백준]2630 색종이 만들기](https://jyukki97.github.io/blog/2020-02-16-2630) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;

int n, c[2200][2200], W = 0, B = 0, D = 0;

void se(int x, int y, int a) {
	bool w = true, b = true, d = true;
	for (int i = 0; i < a; i++)
		for (int t = 0; t < a; t++)
			if (!w && !b && !d) 	break;
			else if (c[x + i][y + t] == -1) {
				w = false;
				b = false;
			}
			else if (c[x + i][y + t]) {
				w = false;
				d = false;
			}
			else {
				d = false;
				b = false;
			}
	W += 1 & w;
	B += 1 & b;
	D += 1 & d;
	if (!w && !b && !d) {
		a /= 3;
		for (int i = 0; i < 3; i++)
			for (int t = 0; t < 3; t++)
				se(x + i * a, y + t * a, a);
	}
}

int main() {
	cin >> n;
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			cin >> c[i][t];
	se(0, 0, n);
	cout << D << endl << W << endl << B << endl;
	return 0;
}
```

