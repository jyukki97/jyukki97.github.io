# 1094 막대기

[https://www.acmicpc.net/problem/1094](http://www.acmicpc.net/problem/1094)

#### **풀이:**
1. 자른 막대기 중 주어진 막대기보다 작은 값 중 최댓값을 주어진 막대기에 계속 뺀다.
2. 뺄때마다 카운트를 증가시키면서 반복한다

#### **코드:**

```
#include <iostream>
using namespace std;
int main(void) {
	int x, temp = 64, cnt = 0;
	cin >> x;
	while (x != 0) {
		if (x >= temp) {
			cnt++;
			x -= temp;
		}
		else
			temp /= 2;
	}
	cout << cnt << endl;
	return 0;
}
```
