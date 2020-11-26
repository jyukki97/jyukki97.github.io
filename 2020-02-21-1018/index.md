# [백준]1018 체스판 다시 칠하기

https://www.acmicpc.net/problem/1018

# 풀이:

(0, 0) ~ (8, 8) ..... (n - 8, m - 8) ~ (n, m) 까지의 모든 8 X 8 체스판을 서치한다.

체스판이 WBWBWB... 순서로 되어있는지 확인 후 안되어 있는 칸이 몇 칸인지 찾는다.

찾아낸 수를 C라고 할 때, 64 - C와 C 중 더 작은 값을 저장한다.

저장된 값들 중 가장 작은 값을 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;

int main() { 
	int n, m, c, ma = 64;
	cin >> n >> m;
	vector<string> a(n);
	for (int i = 0; i < n; i++)
		cin >> a[i];
	for (int i = 0; i < n - 7; i++) {
		for (int t = 0; t < m - 7; t++) {
			c = 0;
			for (int y = 0; y < 8; y++)
				for (int u = 0; u < 8; u++) {
					bool b = (y % 2) ^ (u % 2) ^ (a[i + y][t + u] == 'B' ? 1 : 0);
					c += b;
				}
			c = min(c, 64 - c);
			ma = min(ma, c);
		}
	}	
	cout << ma << endl;
	return 0;
}
```

