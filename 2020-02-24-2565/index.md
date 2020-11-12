# [백준]2565 전깃줄

https://www.acmicpc.net/problem/2565

# 풀이:

c[i] = i 위치 이전 값 중 겹치는 것이 없는 갯수의 최대

연결된 전깃줄 A와 전깃줄 B 를 배열에 저장한다.

저장된 배열을 전깃줄 A를 기준으로 정렬한다.

첫번째 원소부터, 이전 원소 중 전깃줄 B가 더 작은 값 중 c[i] 의 최댓값 + 1을 저장한다.

max값에 c[i]의 최댓값  + 1 중 최댓값을 저장한다.

n - max값을 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int n, a, b, c[101], ma = 0;
vector<pair<int, int>> v;
int main() {
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> a >> b;
		v.push_back(pair<int, int>(a, b));
	}
	sort(v.begin(), v.end());
	for (int i = 0; i < n; i++) {
		for (int t = 0; t < i; t++)
			if (v[i].second > v[t].second)
				c[i] = max(c[i], c[t] + 1);
		ma = max(ma, c[i] + 1);
	}
	cout << n - ma << endl;
	return 0;
}
```

