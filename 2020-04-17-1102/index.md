# [백준]1102 발전소

https://www.acmicpc.net/problem/1102

# 풀이:

발전소의 현재 상태를 2진수로 표현한다.

ex) YNN -> 100

l : 발전소의 현재 상태를 2진수로 표현한 값

z : 발전소가 현재 켜져있는 갯수

z가 p보다 크거나 같아진다면 반복을 종료한다.

d[x] : x상태인 발전소를 만드는데 필요한 비용

d[x] = min(d[x], B(x | (1<<y), z + 1) + a\[u][y])

현재 발전소의 상태에서 안켜진 부분을 키되, 가장 적은 비용으로 킨 후 z를 + 1 한다.



p값이 0이라면 발전소를 킬 필요가 없으므로 0을 출력

p값보다 시작 발전소의 켜져있는 갯수가 더 크다면, 0을 출력



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, l, i, t, s, a[20][20], d[(1 << 17)]; char c[20];
int B(int x, int z) {
	if (z >= m || !m || m <= s) return	0;
	if (d[x] != 987654321)	return d[x];
	for (int y = 0; y < n; y++)
		if (!(x & (1 << y)))
			for (int u = 0; u < n; u++)
				if (x & (1 << u))d[x] = min(d[x], B(x|(1 << y), z + 1) + a[u][y]);
	return d[x];
}
int main() {
	cin >> n;
	fill(d, d + (1 << n), 987654321);
	for (; i < n; i++)for (t = 0; t < n; t++)cin >> a[i][t];
	for (i = 0; i < n; l |= c[i] == 'Y' ? 1 << i : 0, s += c[i++] == 'Y' ? 1 : 0) 			cin >> c[i];
	cin >> m;
    i = B(l, s);
	printf("%d", i == 987654321 ? -1 : i);
}
```

