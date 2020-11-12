# [백준]9325 얼마?

https://www.acmicpc.net/problem/9325

# 풀이:

각 케이스 마다 자동차의 가격에 옵션의 가격을 더하여 출력한다.

# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	int T, n, a, b, c;
	cin >> T;
	while (T--) {
		cin >> a >> n;
		while (n--) { cin >> b >> c; a += b * c; }
		cout << a << endl;
	}
}
```

