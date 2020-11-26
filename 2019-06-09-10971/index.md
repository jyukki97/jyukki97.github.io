# [백준]10971 외판원 순회 2

[https://www.acmicpc.net/problem/10971](http://www.acmicpc.net/problem/10971)

# **풀이:**
1. [[백준]2098 외판원순회](https://jyukki97.github.io/blog/2019-06-01-2098/)  와 같으므로 참고

# **코드:**
사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int w[17][17],d[17][100000], n;
int T(int a, int b) {
	if ((1 << n) - 1 == b && w[a][0] != 0)
		return w[a][0];
	int &r = d[a][b];
	if (r > 0)
		return r;
	r = 100000000;
	for (int i = 0; i < n; i++)
		if (w[a][i] != 0 && (b & (1 << i)) == 0)
			r = min(r, w[a][i] + T(i, b | (1 << i)));
	return r;
}
int main(void) {
	cin >> n;
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			cin >> w[i][t];
	cout << T(0, 1) << endl;
	return 0;
}
```
