# [백준]1388 바닥 장식

https://www.acmicpc.net/problem/1388

# 풀이:

같은 행에  연속된 '-' 이 몇 쌍이 있는지 센다.



같은 방식으로



같은 열에 연속된 '|' 이 몇 쌍이 있는지 센다.



두 수를 더하여 출력한다. 



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, t, c; string s[105];
int main() {
	cin >> n >> m;
	for (; i < n; i++)	cin >> s[i];
	for (i = 0; i < n; i++)
		for (t = 0; t < m; t++) {
			if (s[i][t] == '-')if (t == m - 1 || s[i][t + 1] == '|')c++;
			if (s[i][t] == '|')if (i == n - 1 || s[i + 1][t] == '-')c++;
		}
	cout << c << endl;
}
```

