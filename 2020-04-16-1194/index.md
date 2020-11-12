# [백준]1194 달이 차오른다, 가자

https://www.acmicpc.net/problem/1194

# 풀이:

b\[x]\[y][key] : key를 들고, (x, y) 방문했다면, 1, 방문하지 않았다면 0



0부터 BFS를 시작한다.

오른쪽, 왼쪽, 위, 아래를 갈 수 있는데,

만약 갈 수 있는곳이 빈 곳(' . ') 이고, 방문하지 않았다면, 방문하고, 방문표시를 한다.

만약 갈 수 있는 곳이 문(대문자) 이고, 방문하지 않았다면, 현재 key가 있는지 확인하고, key가 있다면

방문하고, 방문표시를 한다.

만약 갈 수 있는 곳이 열쇠(소문자) 라면, 얻은 열쇠를 key값에 적용시켜준다.



출구('1') 를 만난다면 반복을 중단한다.



미로를 탈출했다면, 이동 횟수의 최솟값을, 탈출하지 못했다면 -1을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m, i, t, w, e, r, f, b[55][55][35], x[4] = { 1,0,0,-1 }, y[4] = { 0,1,-1,0 }; char c[55][55];
int main() {
	cin >> n >> m;
	queue<pair<pair<int, int>, int>> q;
	for (; i < n; i++) 
		for (t = 0; t < m; t++) {
			cin >> c[i][t];
			if (c[i][t] == '0')	q.push({ { i,t },0 }), b[i][t][0] = 1;
		}
	for (i = 0; !f && !q.empty(); i++) {
		queue<pair<pair<int, int>,int>> p;
		while (!q.empty()) {
			w = q.front().first.first, e = q.front().first.second,
            	r = q.front().second, q.pop();
			if (c[w][e] == '1') {
				f = 1;
				break;
			}
			for (t = 0; t < 4; w -= x[t], e -= y[t], t++) {
				w += x[t], e += y[t];
				if (w < 0 || w >= n || e < 0 || e >= m)	continue;
				if ((!isalpha(c[w][e]) && c[w][e] != '#' && !b[w][e][r])
					|| (isupper(c[w][e]) && !b[w][e][r] 
                        && (r & (1 << (c[w][e] - 65)))))
					b[w][e][r] = 1, p.push({ {w,e},r });
				if (islower(c[w][e]) && !b[w][e][r | (1 << (c[w][e] - 97))])
					b[w][e][r | (1 << (c[w][e] - 97))] = 1, 
                		p.push({ {w,e}, r | (1 << (c[w][e] - 97)) });
			}
		}
		q = p;
	}
	printf("%d", f ? i - 1 : -1);
}
```

