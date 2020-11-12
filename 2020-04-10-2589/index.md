# [백준]2589 보물섬

https://www.acmicpc.net/problem/2589

# 풀이:

모든 L을 전부 찾는다.

현재 L에서 최단 거리로 가장 먼 거리가

현재 저장된 거리보다 크다면 현재 저장된 거리를 바꾼다.

최대 거리를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m, i, t, s, y; string c[55];
int main() {
	cin >> n >> m;
	for (; i < n; i++)	cin >> c[i];
	for (i = 0; i < n; i++)	
		for (t = 0; t < m; t++, s = y - 1 > s ? y - 1: s)
			if (c[i][t] == 'L') {
				int w, e, b[55][55] = { 0 };
				queue<pair<int, int>> q;
				q.push({ i,t }), b[i][t]++;
				for (y = 0;!q.empty(); y++) {
					queue<pair<int, int>> p;
					while (!q.empty()) {
						w = q.front().first, e = q.front().second, q.pop();
						if (w > 0 && !b[w - 1][e] && c[w - 1][e] == 'L') 
							b[w - 1][e]++, p.push({ w - 1,e });
						if (e > 0 && !b[w][e - 1] && c[w][e - 1] == 'L')
							b[w][e - 1]++, p.push({ w,e - 1 });
						if (w + 1 < n && !b[w + 1][e] && c[w + 1][e] == 'L')
							b[w + 1][e]++, p.push({ w + 1,e });
						if (e + 1 < m && !b[w][e + 1] && c[w][e + 1] == 'L')
							b[w][e + 1]++, p.push({ w,e + 1 });
					}
					q = p;
				}
			}
	cout << s << endl;
}
```

