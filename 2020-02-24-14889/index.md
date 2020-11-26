# [백준]14889 스타트와 링크

https://www.acmicpc.net/problem/14889

# 풀이:

n / 2 명의 스타트 팀과 n / 2 팀의 링크팀을 만든다.

스타트팀만 만든다면, 자동적으로 남는 사람들은 링크팀이된다.

구하는 팀에 1은 무조건 들어가도록한다. (1을 포함한 팀을 전부 구한다면, 1을 포함하지 않는 팀은 상대팀에 모두 있기 때문에)



스타트팀의 모든 Sij 값의 합과 링크팀의 모든 Sij 값의 합의 차이를 구한다.



구한 차이들 중 가장 작은 값을 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;

int n, m[21][21], mn = 100000, start, link;
bool s[21];

void st(int a, int b) {
	if (a == n / 2) {
		start = 0;
		link = 0;
		for (int i = 0; i < n; i++)
			if (s[i]) {
				for (int t = i + 1; t < n; t++)
					if (s[t])
						start += m[i][t] + m[t][i];
			}
			else
				for (int t = i + 1; t < n; t++)
					if (!s[t])
						link += m[i][t] + m[t][i];
		start = start > link ? start - link : link - start;
		mn = min(mn, start);
	}
	else
		for (int i = b; i < n; i++) {
			s[i] = true;
			st(a + 1, i + 1);
			s[i] = false;
		}
}

int main() {
	cin >> n;
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			cin >> m[i][t];
	s[0] = true;
	st(1, 1);
	cout << mn << endl;
	return 0;
}
```

