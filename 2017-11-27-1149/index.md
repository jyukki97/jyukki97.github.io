# [백준]1149 RGB거리


https://www.acmicpc.net/problem/1149

# **풀이:**
1. r,g,b를 각각 b[0], b[1], b[2] 로 둠.
2. r을 선택했다면 이전에서 g,b 중 작은값에 이번에 r값을 더하는 식으로 r,g,b 반복
3. r,g,b 최종값에서 가장 최소값 출력

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;

int main(void) {
	int n;
	cin >> n;
	int a[3001];
	int b[3];
	for (int i = 0; i < n*3; i++) {
		cin >> a[i];
	}
	for (int i = 1; i < n; i++) {
		b[0] = a[0];
		b[1] = a[1];
		b[2] = a[2];
		a[0] = min(b[1], b[2]) + a[i * 3];
		a[1] = min(b[0], b[2]) + a[(i * 3) + 1];
		a[2] = min(b[0], b[1]) + a[(i * 3) + 2];
	}
	int temp = min(a[0], a[1]);
	cout << min(temp, a[2]) << endl;
	return 0;
}
```


