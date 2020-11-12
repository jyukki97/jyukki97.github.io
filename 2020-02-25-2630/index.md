# [백준]2630 색종이 만들기

https://www.acmicpc.net/problem/2630

# 풀이:

n을 2로 나누어 가며 1로 이루어진 곳인지 0으로 이루어진 곳인지 판단한다.



0으로 이루어져있다면 W를 +1 , 1로 이루어져있다면 B를 +1 해준다.



하얀색 색종이와 파란색 색종이의 갯수를 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;

int n, c[129][129], W = 0, B = 0;

void se(int x, int y, int a) {
	if (x >= n || y >= n || !a)	return;
	bool w = true, b = true;
	for (int i = 0; i < a; i++)
		for (int t = 0; t < a; t++)
			if (!w && !b) 	break;
			else if (c[x + i][y + t])	w = false;
			else  b = false;
	W += 1 & w;
	B += 1 & b;
	if (!w && !b){
		a /= 2;
		se(x, y, a);
		se(x + a, y, a);
		se(x, y + a, a);
		se(x + a, y + a, a);
	}
}

int main() {
	cin >> n;
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			cin >> c[i][t];
	se(0, 0, n);
	cout << W << endl << B << endl;
	return 0;
}
```

