# [백준]1697 숨바꼭질

https://www.acmicpc.net/problem/1697

# 풀이:

현재 위치를 x라고 할 때, x + 1, x - 1, x * 2 위치를 BFS 를 통해 하나씩 찾아간다.

동생의 위치와 같아진다면 몇번 이동했는지 출력한다.



###### x + 1 은 동생의 위치보다 커질 필요가없으므로 동생의 위치보다 작을때만 이동한다.

###### x * 2 는 동생의 위치 + 1 보다 크다면 (x - 2) * 2 를 하는 것이 이득이므로 제외한다.

###### 현재 위치는 0보다 작아질 수 없으므로 제외한다.

###### 이미 한번 방문한 위치는 다시 방문할 필요없으므로 제외시킨다. 



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <queue>
using namespace std;
int n, m, k, i = 1, q = 0, dps;
bool a[100005];
queue<int> dp;
int main() {
	cin >> n >> k;
	dp.push(n);
	a[n] = true;
	while (!q) {
		dps = dp.size();
		while (dps--) {
			m = dp.front();
			if (m == k) {
				q = i;
				break;
			}
			if (m > 0 && !a[m - 1]) {
				dp.push(m - 1);
				a[m - 1] = true;
			}
			if (m <= k && !a[m + 1]) {
				dp.push(m + 1);
				a[m + 1] = true;
			}
			if (m + m < k + 2 && !a[m + m]) {
				dp.push(m + m);
				a[m + m] = true;
			}
			dp.pop();
		}
		i++;
	}
	cout << q - 1 << endl;
}
```

