# [백준]12778 CTP공국으로 이민 가자


https://www.acmicpc.net/problem/12778

# 풀이:

만약 C라면,

문자열을 숫자로 출력한다.

만약 N이라면,

숫자를 문자열로 출력한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
using namespace std;

int main() {
	int a, i, n;
	char b;
	cin >> n;
	while (n--) {
		cin >> a >> b;
		if (b == 'C') {
			for (i = 0; i < a; i++) {
				char c;
				cin >> c;
				cout << (int)(c - 'A' + 1) << " ";
			}
		}
		else {
			for (i = 0; i < a; i++) {
				int c;
				cin >> c;
				cout << (char)('A' + c - 1) << " ";
			}
		}
		cout << endl;
	}
}
```
