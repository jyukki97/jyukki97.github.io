# [백준]1937 욕심쟁이 판다


[https://www.acmicpc.net/problem/1937](http://www.acmicpc.net/problem/1937)

# **풀이:**
1. k\[a][b]를 (a , b)지점에서 시작한 판다가 살아남은 최대 일수라고 한다.
2. (a, b) 주변 십자가 방향 지점( (1,0), (-1, 0), (0, 1), (0, -1)) 에서 대나무의 양이 (a, b) 보다 낮다면 그 지점에 최대 일수에서 +1 한 값이 k\[a][b] 값이 된다.
3. 높은 값에서 낮은값으로 찾아가면서 최대 일수를 구한다.
4. 시간초과가 날 수 있으므로 메모이제이션을 통해 시행횟수를 제한해준다.    

# **코드:**
사용언어 : c++

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, s[510][510], k[510][510];
int dx[] = { 1,0,0,-1 };
int dy[] = { 0,1,-1,0 };
int panda(int a, int b){
	for (int y = 0; y < 4; y++)
		if (a + dy[y] >= 0 && a + dy[y] < n && b + dx[y] >= 0 && b + dx[y] < n)
			if (s[a][b] < s[a + dy[y]][b + dx[y]]) {
				if(k[a + dy[y]][b + dx[y]] == 1)
					k[a][b] = max(k[a][b], panda(a + dy[y], b + dx[y]) + 1);
				else
					k[a][b] = max(k[a][b], k[a + dy[y]][b + dx[y]] + 1);
			}
	return k[a][b];
}
int main(void) {
	cin >> n;
	int m = 1;
	fill(&k[0][0], &k[n][n], 1);
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			cin >> s[i][t];
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			m = max(m, panda(i, t));
	cout << m << endl;
	return 0;
}
```


