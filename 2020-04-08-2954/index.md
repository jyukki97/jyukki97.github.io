# [백준]2954 창영이의 일기장

https://www.acmicpc.net/problem/2954

# 풀이:

문자열을 하나씩 읽는 중 모음이 나온다면, 그 다음글자와 다다음 글자를 삭제한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;
int i, c; string s;
int main() {
	getline(cin, s);
	for (i = 0; i < s.size(); i++)
		if (s[i] == 'a' || s[i] == 'e' || s[i] == 'i' || s[i] == 'o' || s[i] == 'u')
			s.erase(i + 1, 2);
	cout << s << endl;
}
```

