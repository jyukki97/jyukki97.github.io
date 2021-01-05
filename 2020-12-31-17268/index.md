# [백준]17268 미팅의 저주


https://www.acmicpc.net/problem/17268

# 풀이:

n = 2 .... 1

n = 4 .... 2

n = 6 .... 5

n = 8 .... 14

.

.

.



1, 2, 5, 14 ... 로 진행되는 수열인 카탈란 수 이다.



카탈란 수는
$$
C_i = {2i \choose i} - {2i \choose i + 1}
$$
이다.



이를 점화식으로 표현하면
$$
C_n = \sum_{i=0}^{n-1}C_iC_{n-1-i}
$$
이 된다.





# **코드:** 

사용언어 : c++

```c++
#include <iostream>
using namespace std;
long long dp[5005] = { 1 }, n, i, t;
int main() {
	cin >> n;
	for (i = 1; i <= n / 2; i++) {
		for (t = 0; t < i; t++) {
			dp[i] = (dp[i] + dp[t] * dp[i - 1 - t]) % 987654321;
		}
	}
	cout << dp[n / 2] << endl;
}
```
