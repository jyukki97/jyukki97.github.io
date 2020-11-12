# [백준]12865 평범한 배낭

https://www.acmicpc.net/problem/12865

# 풀이:

DP[i] : i 무게일 때, 배낭에 넣을 수 있는 물건의 가치의 최댓값

DP[i + w] = max(DP[i + w], DP[i] + v)

무게가 i + w 일 때, 최댓값은 이전에 있었던 i + w 일때의 값과, i 에 있는 값에 w 무게 물건의 가치인 v를 더한 값 중 최댓값이다.

(DP를 DP\[2][100001] 처럼 두개로 나누어 놓은 이유는 물건의 갯수가 1개씩이기 때문에 물건 중복을 피하기위해 나누어놓았다.)

ex) 무게가 4이고, 가치가 5일때, DP[4] = 5 가 되지만, DP[8] = DP[4] + 5 가 되어 10이 되는 불상사가 일어날 수 있기 때문에, 두개로 나누어 놓앗다. 



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;

int n, k, w, v, c[2][100001], ma = 0;

int main() {
	cin >> n >> k;
	for (int i = 0; i < n; i++) {
		cin >> w >> v;
		for (int t = 0; t < w; t++)
			c[i % 2][t] = max(c[(i + 1) % 2][t], c[i % 2][t]);
		for (int t = 0; t <= k - w; t++) {
			c[i % 2][w + t] = max(c[(i + 1) % 2][w + t], v + c[(i + 1) % 2][t]);
			ma = max(ma, c[i % 2][w + t]);
		}
	}
	cout << ma << endl;
	return 0;
}
```

