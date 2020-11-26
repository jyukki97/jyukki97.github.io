# [백준]5069 미로에 갇힌 상근


[https://www.acmicpc.net/problem/5069](http://www.acmicpc.net/problem/5069)

# **풀이:**
1. s[n][t][y]를 n번 이동해서 (t, y)인 방으로 다시 돌아오는 경우의 수라고 한다.
2. 처음 상근이가 있는 방을 (10, 10)이라고 한다(n의 최대 수가 14 이므로 10칸을 넘어가지 않기 때문에)
3. s[n][10][10] 은 n번 이동해서 상근이가 있는 방으로 돌아와야하므로 상근이의 근처에 있는 모든 n-1번 이동하여 돌아오는 경우의 수들의 합과 같다.
4. 즉 s[n][10][10] = s[n-1][10][11] + s[n-1][10][9] + s[n-1][11][11] + s[n-1][11][10] + s[n-1][9][9] + s[n-1][9][10]    

# **코드:**
사용언어 : c++

```c++
#include <iostream>
using namespace std;
int s[15][21][21];
int dy[] = { 0,0,1,1,-1,-1 };
int dx[] = { 1,-1,1,0,-1,0 };
int main(void) {
	int T, a;
	cin >> T;
	s[0][10][10] = 1;
	for (int i = 1; i < 15; i++)
		for (int t = 1; t < 21; t++)
			for (int y = 1; y < 21; y++)
				for (int u = 0; u < 6; u++)
					if (t + dx[u] > 0 && t + dx[u] < 21 && y + dy[u] > 0 && y + dy[u] < 21)
						s[i][t][y] += s[i - 1][t + dx[u]][y + dy[u]];
	while (T--) {
		cin >> a;
		cout << s[a][10][10] << endl;
	}
	return 0;
}
```
