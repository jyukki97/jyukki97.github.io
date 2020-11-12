# [백준]3908 서로 다른 소수의 합


[https://www.acmicpc.net/problem/3908](http://www.acmicpc.net/problem/3908)

# **풀이:**
1. 소수를 찾는다.
2. 소수를 하나씩 추가해가면서 a\[n][k]를 찾는다.
3. a\[n][k]
	: 양의 정수 n을 서로 다른 k개의 소수의 합으로 나타낼 수 있는 최대의 경우의 수

# **코드:**

```C++
#include <iostream>
#include <vector>
#include <math.h>
#include <string.h>
using namespace std;
int	T, n, k, a[1122][16] = { 0 };
bool isprime[1122];
vector<int> b;
int prime() {
	memset(isprime, 1, sizeof(isprime));
	isprime[0] = isprime[1] = false;
	for (int i = 2; i < sqrt(1122); i++)
		if(isprime[i])
			for (int t = i * i; t < 1122; t += i)
				isprime[t] = false;
	for (int i = 2; i < 1122; i++) 
		if (isprime[i]) b.push_back(i);
}
int main(void) {
	prime();
	cin >> T;
	a[0][0] = 1;
	for (int i = 0; i < b.size(); i++)
		for (int t = 1121; t >= b[i]; t--)
			for (int y = 1; y <= 14; y++)
				a[t][y] += a[t - b[i]][y - 1];
	for (int i = 0; i < T; i++) {
		cin >> n >> k;
		cout << a[n][k] << endl;
	}
	return 0;
}
```
