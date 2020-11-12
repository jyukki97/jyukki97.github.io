# 1977 완전제곱수

[https://www.acmicpc.net/problem/1977](http://www.acmicpc.net/problem/1977)

#### **풀이:**
1. m 이상 n이하의 완전제곱수를 다 더한 후 최솟값을 출력
2. 만약 sum이 0이라면 -1을 출력

#### **코드:**

```
#include <iostream>
using namespace std;
int main(void) {
	int m, n, mini = 0, sum = 0, i = 1;
	cin >> m >> n;
	while (true) {
		if (i*i >= m) {
			if (i * i > n)
				break;
			if (mini == 0)
				mini = i * i;
			sum += i * i;
		}
		i++;
	}
	if (sum == 0)
		cout << "-1" << endl;
	else
		cout << sum << endl << mini << endl;
	return 0;
}
```
