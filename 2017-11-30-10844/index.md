# [백준]10844 쉬운 계단 수


[https://www.acmicpc.net/problem/10844](http://www.acmicpc.net/problem/10844)

# **풀이:**
1. a[i][t] 는 길이가 i인 숫자에서 1의 자릿 수가 t일 때의 경우의 수
2. t가 0 이면 a[i][t] = a[i - 1][t + 1]
3. t가 9 이면 a[i][t] = a[i - 1][t - 1]
4. 둘다 아니면 a[i][t] = (a[i - 1][t - 1] + a[i - 1][t + 1])
5. 이 때 오버플로우가 발생하므로 각각의 계산에 1000000000을 나눠준다.

# **코드:**

```C++
#include <iostream>
using namespace std;
long long a[101][10] = { 0 };
int main(void) {
	int n;
	cin >> n;
	long long cnt = 0;
	for (int i = 1; i < 10; i++) {
		a[0][i] = 1;
	}
	for (int i = 1; i < n; i++) {
		for (int t = 0; t < 10; t++) {
			if (t == 0)
				a[i][t] = a[i - 1][t + 1] % 1000000000;
			else if (t == 9)
				a[i][t] = a[i - 1][t - 1] % 1000000000;
			else
				a[i][t] = (a[i - 1][t - 1] + a[i - 1][t + 1]) % 1000000000;
		}
	}
	for (int i = 0; i < 10; i++) {
		cnt += a[n - 1][i] % 1000000000;
	}
	cout << cnt % 1000000000 << endl;
	return 0;
}
```

