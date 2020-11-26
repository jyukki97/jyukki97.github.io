# [프로그래머스]시저 암호

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 문자열 s를 n만큼 밀어서 나온 다른 알파벳의 결과값을 리턴한다.
2. 중간에 공백문자가 있을 수 있으니 주의한다.
3. 'z'를 밀 경우 'A'가 아니라 'a'가 나와야 하므로 주의한다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(string s, int n) {
	for (int i = 0;i < s.size();i++) {
		if (isalpha(s[i])) {
			if (s[i] + n > 'z') {
				s[i] = 96 + (s[i] + n) % 'z';
			}
			else if (s[i] <= 'Z' && s[i] + n > 'Z') {
				s[i] = 64 + (s[i] + n) % 'Z';
			}
			else
				s[i] += n;
		}
	}
    return s;
}
```

