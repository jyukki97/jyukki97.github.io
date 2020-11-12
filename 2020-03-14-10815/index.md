# [백준]10815 숫자 카드

https://www.acmicpc.net/problem/10815

# 풀이:

[[C++\]lower_bound, upper_bound](https://jyukki97.github.io/learn/2020-02-19-bound/) 참고



###### cin, cout 은 시간초과가 날 수 있으므로 주의하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, i, k, a[500002];
int main() {
	cin >> n;
	for (i = 0; i < n; i++)	cin >> a[i];
	sort(a, a + n);
	cin >> m;
	while (m--) {
		cin >> k;
		if (*lower_bound(a, a + n, k) == k)	cout << "1 ";
		else	cout << "0 ";
	}
	cout << endl;
}
```

