# [백준]2583 영역 구하기

https://www.acmicpc.net/problem/2583

# 풀이:

직사각형이 들어있는 곳을 1,

없는곳을 0으로 해놓은 배열을 만든다.

배열을 순회하며, 현재 값이 0 이라면, 영역의 개수를 +1 해주고,

연결된 모든 영역을 순회하여 1로 바꿔주고, 영역의 넓이를 배열에 저장한다.

배열의 모든 숫자가 1이라면,

영역의 개수를 출력하고,

각 영역의 넓이를 오름차순으로 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, k, i, t, a[102][102], x1, x2, yl, y2, s = 0, b[5002];
void A(int x, int y) {
	a[x][y] = 1, b[s - 1]++;
	if (x > 0 && !a[x - 1][y]) A(x - 1, y);
	if (y > 0 && !a[x][y - 1]) A(x, y - 1);
	if (x + 1 < n && !a[x + 1][y]) A(x + 1, y);
	if (y + 1 < m && !a[x][y + 1]) A(x, y + 1);
}
int main() {
	cin >> m >> n >> k;
	while(k--) {
		cin >> x1 >> yl >> x2 >> y2;
		for (i = x1; i < x2; i++)	for (t = yl; t < y2; t++)	a[i][t] = 1;
	}
	for (i = 0; i < n; i++)	for (t = 0; t < m; t++)	if (!a[i][t])	s++, A(i, t);
	cout << s << endl;
	sort(b, b + s);
	for (i = 0; i < s; i++)	cout << b[i] << " ";
	cout << endl;
}
```

