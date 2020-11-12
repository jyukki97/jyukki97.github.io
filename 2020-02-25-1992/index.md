# [백준]1992 쿼드트리

https://www.acmicpc.net/problem/1992

# 풀이:

[[백준]2630 색종이 만들기](https://jyukki97.github.io/blog/2020-02-16-2630) 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;

int n;
string s, c[65];

void se(int x, int y, int a) {
	if (x >= n || y >= n || !a)	return;
	bool w = true, b = true;
	for (int i = 0; i < a; i++)
		for (int t = 0; t < a; t++)
			if (!w && !b) 	break;
			else if (c[x + i][y + t] == '1')	w = false;
			else  b = false;
	if (w)	s += '0';
	else if (b) s += '1';
	else{
		s += '(';
		a /= 2;
		se(x, y, a);
		se(x, y + a, a);
		se(x + a, y, a);
		se(x + a, y + a, a);
		s += ')';
	}
}

int main() {
	cin >> n;
	for (int i = 0; i < n; i++)
		cin >> c[i];
	se(0, 0, n);
	cout << s << endl;
	return 0;
}
```

