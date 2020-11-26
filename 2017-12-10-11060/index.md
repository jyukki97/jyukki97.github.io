# [백준]11060 점프 점프


[https://www.acmicpc.net/problem/11060](http://www.acmicpc.net/problem/11060)

# **풀이:**
1. cnt[i] 는 i번째 에서의 최소 가짓수
2. cnt를 모두 최댓값으로 채운 후
3. a[i] 이하의 값으로 점프할 때 마다
4. cnt[i + t] 값을 min(cnt[i + t], cnt[i] + 1) 로 해줌으로써 최소 가짓수를 찾는다
5. 만약 도착점의 값이 처음 채운 1001과 같다면 갈 수 없는 경우이므로 -1을 출력한다.

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[1001], cnt[1001];
int main(void) {
	int n;
	cin >> n;
	fill_n(cnt, n, 1001);
	for (int i = 0; i < n; i++) {
		cin >> a[i];
	}
	cnt[0] = 0;
	for (int i = 0; i < n; i++) {
		for (int t = 1; t <= a[i]; t++) {
			cnt[i + t] = min(cnt[i + t], cnt[i] + 1);
		}
	}
	if (cnt[n - 1] == 1001)
		cout << "-1" << endl;
	else
		cout << cnt[n - 1] << endl;
	return 0;
}
```


