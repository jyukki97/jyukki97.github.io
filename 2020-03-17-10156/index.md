# [백준]10156 과자

https://www.acmicpc.net/problem/10156

# 풀이:

과자 한개의 가격 * 과자의 개수 - 현재 가진 돈 을 출력한다.

만약 출력값이 음수라면 0을 출력한다. (필요한 돈보다 가진돈이 많은 것이므로 부모님께 받을 필요없음.)



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int k, n, m;
int main() {
	cin >> k >> n >> m;
	k = k * n - m;
	if (k < 0)	k = 0;
	cout << k << endl;
}
```

