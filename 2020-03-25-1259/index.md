# [백준]1259 팰린드롬수

https://www.acmicpc.net/problem/1259

# 풀이:

팰린드롬 이라면 yes 를 아니라면 no를 출력한다.

맨 첫 글자와 맨 마지막글자 가 같은지

i번째 글자와 size() - i - 1 번째 글자가 같은지

를 판단하여, 만약 하나라도 다르다면 no를 전부 같다면 yes를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	while (1) {
		string s;
		int i, t = 0;
		cin >> s;
		if (s == "0")	break;
		for (i = 0; i < s.size() / 2; i++) if (s[i] != s[s.size() - i - 1])	t = 1;
		printf("%s\n", t ? "no" : "yes");
	}
}
```

