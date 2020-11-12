# [백준]4963 섬의 개수

https://www.acmicpc.net/problem/4963

# 풀이:

모든 지도를 순회한다.

만약 지도의 한 부분이 땅이라면,

연결된 모든 땅을 바다로 바꾼 후 섬의 개수를 +1 해준다.

지도의 모든 부분이 바다로 바뀔때까지 반복한다.

섬의 개수를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, t, a[52][52], c;
void I(int x, int y) {
	a[x][y] = 0;
	if (x > 0 && y > 0 && a[x - 1][y - 1]) I(x - 1, y - 1);
	if (x > 0 && a[x - 1][y]) I(x - 1, y);
	if (x > 0 && y + 1 < n && a[x - 1][y + 1]) I(x - 1, y + 1);
	if (y > 0 && a[x][y - 1]) I(x, y - 1);
	if (y + 1 < n && a[x][y + 1]) I(x, y + 1);
	if (x + 1 < m && y > 0 && a[x + 1][y - 1]) I(x + 1, y - 1);
	if (x + 1 < m && a[x + 1][y]) I(x + 1, y);
	if (x + 1 < m && y + 1 < n && a[x + 1][y + 1]) I(x + 1, y + 1);
}
int main() {
	while (1) {
		cin >> n >> m;
		c = 0;
		if (!n)	break;
		for (i = 0; i < m; i++)	for (t = 0; t < n; t++)	cin >> a[i][t];
		for (i = 0; i < m; i++)	for (t = 0; t < n; t++)	if (a[i][t])c++, I(i, t);
		cout << c << endl;
	}
}
```

