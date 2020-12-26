# [백준]12780 원피스


https://www.acmicpc.net/problem/12780

# 풀이:

H의 1번 문자열부터 끝까지 검사하며 N이 몇 번 등장하는지 확인한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <string>
using namespace std;

int main() {
	string s, a;
	int c = 0;
	cin >> s >> a;
	for (int i = 0; i <= s.length() - a.length(); i++) {
		if (s.substr(i, a.length()) == a) c++;
	}
	cout << c << endl;
}
```
