# [백준]17271 리그 오브 레전설 (Small)


https://www.acmicpc.net/problem/17271

# 풀이:

[[백준\]2624 동전 바꿔주기](https://jyukki97.github.io/2018-01-11-2624/) 참고



# **코드:** 

사용언어 : c++

```c++
#include<iostream>
using namespace std;
long long d[10005] = { 1,1 }, n, m, i;
int main() {
	cin >> n >> m;
	for (i = 2; i <= n; i++)
		d[i] = (d[i - 1] + (i - m >= 0 ? d[i - m] : 0)) % 1000000007;
	cout << d[n] << endl;
}
```
