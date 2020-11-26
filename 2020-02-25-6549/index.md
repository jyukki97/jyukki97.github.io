# [백준]6549 히스토그램에서 가장 큰 직사각형

https://www.acmicpc.net/problem/6549

# 풀이:

값을 하나씩 받아온다.



현재 값보다 스택에 있는 값이 더 크다면,

max(현재 max값, 스택의 탑값 * (스택의 탑 바로 전 값의 위치와 현재 위치의 차이)) 을 수행하고, 현재 탑에 있는 값을 pop한다.

스택에 모든 값이 현재 있는 값보다 작거나 같다면, 스택에 현재 값을 push한다.



모든 값을 받았다면,  스택이 빌 때까지 

max(현재 max값, 스택의 탑값 * (스택의 탑 바로 전 값의 위치와 전체 히스토그램의 길이의 차이))

를 수행한다.



히스토그램의 길이가 0일경우 반복을 중지한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <stack>
#include <algorithm>
using namespace std;
typedef long long ll;
ll n, m, i, ma, c;
int main() {
	while (1) {
		ma = 0;
		cin >> n;
		if (!n)	break;
		stack<pair<ll, ll>> a;
		a.push({ 0, 0 });
		for (i = 1; i <= n; i++) {
			cin >> m;
			while (m < a.top().second) {
				c = a.top().second;
				a.pop();
				ma = max(ma, c * (i - a.top().first - 1));
			}
			a.push({ i, m });
		}
		c = a.top().second;
		a.pop();
		while (!a.empty()) {
			ma = max(ma, c * (n - a.top().first));
			c = a.top().second;
			a.pop();
		}
		cout << ma << endl;
	}
	return 0;
}

```

