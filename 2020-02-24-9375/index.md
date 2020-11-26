# [백준]9375 패션왕 신해빈

https://www.acmicpc.net/problem/9375

# 풀이:

[프로그래머스\]위장](https://jyukki97.github.io/blog/2019-12-29-camouflage/) 을 참고



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <string>
#include <map>
using namespace std;

int main() {
	int n, m, ma;
	cin >> n;
	while (n--) {
		ma = 1;
		cin >> m;
		string s;
		map<string, int> a;
		for (int i = 0; i < m; i++) {
			cin >> s >> s;
			a[s]++;
		}
		for (auto i = a.begin(); i != a.end(); i++)
			ma *= i->second + 1;
		cout << ma - 1 << endl;
	}
	return 0;
}
```

