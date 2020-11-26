# [백준]1365 꼬인 전깃줄

[https://www.acmicpc.net/problem/1365](http://www.acmicpc.net/problem/1365)

# **풀이:**
1. [https://jyukki97.github.io/2352/](https://jyukki97.github.io/2352/) 와 같은 문제이므로 참고

# **코드:**
사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
vector<int>d;
int main(void) {
	int n, s, l;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> s;
		l = lower_bound(d.begin(), d.end(), s) - d.begin();
		if (l == d.size())
			d.push_back(s);
		else
			d[l] = s;
	}
	cout << n - d.size() << endl;
	return 0;
}
```
