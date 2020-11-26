# [백준]2624 동전 바꿔주기


[https://www.acmicpc.net/problem/2624](http://www.acmicpc.net/problem/2624)

# **풀이:**
1. coin[i]
	: i원의 지폐를 동전으로 교환할 수 있는 경우의 수
   
2. 지폐의 가격 + 동전의 가격 * 동전의 개수를 계속 쌓아간다.

# **코드:**

```C++
#include <iostream>
using namespace std;
pair<int, int> a[101];
int coin[10001] = { 0 };
int main(void) {
	int T, k, n, m;
	cin >> T >> k;
	for (int i = 0; i < k; i++) {
		cin >> n >> m;
		a[i] = make_pair(n, m);
	}
	coin[0] = 1;
	for (int i = 0; i < k; i++)
		for (int t = T; t > 0 ; t--)
			for (int y = 1; y <= a[i].second; y++) {
				if (t - (a[i].first * y) >= 0)
					coin[t] += coin[t - (a[i].first * y)];
			}
	cout << coin[T] << endl;
	return 0;
}
```

# **주의 코드:**

1. 백준에서 map을 지원하지 않는건지 내가 map에 이해도가 안좋은건지 위 코드와 같은 코드지만 틀렸다고 한다.

```c++
#include <iostream>
#include <map>
using namespace std;
map<int, int> a;
int coin[10010] = { 0 };
int main(void) {
	int T, k, n, m;
	cin >> T >> k;
	for (int i = 0; i < k; i++) {
		cin >> n >> m;
		a[n] = m;
	}
	coin[0] = 1;
	map<int, int>::iterator itr;
	for (itr = a.begin(); itr != a.end(); itr++)
		for (int t = T; t > 0 ; t--)
			for (int y = 1; y <= itr->second; y++) {
				if (t - (itr->first * y) >= 0)
					coin[t] += coin[t - (itr->first * y)];
			}
	cout << coin[T] << endl;
	return 0;
}
```
