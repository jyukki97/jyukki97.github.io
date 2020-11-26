# [백준]1904 01타일


[https://www.acmicpc.net/problem/1904](http://www.acmicpc.net/problem/1904)

# **풀이:**
1. a[i] 는 길이가 i인 모든 이진수열의 개수
2. a[i] = a[i - 1] + a[i - 2]
3. 주어진 조건에 맞게 15746 으로 나눈 나머지를 출력

# **코드:**

```c++
#include <iostream>
using namespace std;
int a[1000001] = { 1,2 };
int main(void) {
	int n;
	cin >> n;
	for (int i = 2; i < n; i++) {
		a[i] = (a[i - 1] % 15746 + a[i - 2] % 15746) % 15746;
	}
	cout << a[n - 1] << endl;
	return 0;
}
```


