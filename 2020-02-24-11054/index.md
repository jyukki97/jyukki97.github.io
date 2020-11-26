# [백준]11054 가장 긴 바이토닉 부분 수열

https://www.acmicpc.net/problem/11054

# 풀이:

b[i] = i 위치 왼쪽에 있는 값들 중 m[i] 보다 작은 수들의 최대 갯수

s[i] = i 위치 오른쪽에 있는 값들 중 m[i] 보다 작은 수들의 최대 갯수

가장 긴 수열의 길이 = 모든 i 에 대해 (b[i] + s[i] + 1) 의 최댓값



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;

int n, m[1001], b[1001], s[1001], ma = 0;

int main() {
	cin >> n;
	for (int i = 0; i < n; i++)
		cin >> m[i];
	for (int i = n - 2; i >= 0; i--)
		for (int t = n - 1; t > i; t--)
			if (m[i] > m[t])
				s[i] = max(s[i], s[t] + 1);
	for (int i = 0; i < n; i++) {
		for (int t = 0; t < i; t++)
			if (m[i] > m[t])
				b[i] = max(b[i], b[t] + 1);
		ma = max(ma, b[i] + s[i] + 1);
	}
	cout << ma << endl;
	return 0;
}
```

