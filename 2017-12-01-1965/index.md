# [백준]1965 상자넣기


[https://www.acmicpc.net/problem/1965](http://www.acmicpc.net/problem/1965)

# **풀이:**
1. b[i] 가 i 번째 상자를 골랐을 때의 상자의 최대 갯수라고 하자.
2. b[i] = b[i] + 0~i 번째 까지 중 가장 큰 값 이다.

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;

int main(void) {
	int n,temp;
	cin >> n;
	int a[1001] = { 0 };
	int b[1001];
	for (int i = 0; i < n; i++) {
		cin >> a[i];
		b[i] = 1;
	}
	for (int i = 0; i < n; i++) {
		temp = 0;
		for (int t = 0; t <= i; t++) {
			if (a[i] > a[i - t])
				temp = max(b[i - t], temp);
		}
		b[i] += temp;
	}
	for (int i = 0; i < n; i++) {
		temp = max(b[i], temp);
	}
	cout << temp << endl;
	return 0;
}
```


