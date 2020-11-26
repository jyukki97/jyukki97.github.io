# [백준]2468 안전 영역

https://www.acmicpc.net/problem/2468

# 풀이:

물의 높이가 h 일 때,

지역의 높이가 h보다 작거나 같다면 잠겨있는 지역이라고 한다.

모든 지역을 순회하며, 

현재 지역이 잠겨있지 않다면, 방문 표시를 해두고,

왼쪽, 오른쪽, 위, 아래 에 잠겨있지 않은 곳을 순회하며 방문표시를 한다.

연결된 모든 곳을 방문했다면, 안전한 영역을 +1 해준다.



물의 높이를 0 ~ (지역 중 최대 높이)  까지 순회한 후

안전한 영역의 최대치를 출력한다.





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#define F(i,n)for(int i=0;i<n;i++)
using namespace std;
int n, m = 0, a[102][102], b[102][102], s, r = 0;
void A(int x, int y) {
	b[x][y] = 0;
	if (x > 0 && b[x - 1][y])	A(x - 1, y);
	if (y > 0 && b[x][y - 1])	A(x, y - 1);
	if (x + 1 < n && b[x + 1][y])	A(x + 1, y);
	if (y + 1 < n && b[x][y + 1])	A(x, y + 1);
}
int main() {
	cin >> n;
	F(i,n)F(t,n){
		cin >> a[i][t];
		m = m < a[i][t] ? a[i][t] : m;
	}
	while (m--) {
		s = 0;
		F(i, n)	F(t, n)
			if (a[i][t] > m)	b[i][t] = 1;
			else	b[i][t] = 0;
		F(i, n)	F(t, n)	if (b[i][t])	s++, A(i, t);
		r = r < s ? s : r;
	}
	cout << r << endl;
}
```

