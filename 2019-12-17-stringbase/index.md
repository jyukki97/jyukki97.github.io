# [프로그래머스]문자열 다루기 기본

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 문자열 s의 길이가 4 또는 6 이고, 숫자로만 구성되어있는지 확인 후 아니라면 false를 리턴

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

bool solution(string s) {
    bool answer = true;
    if (s.length() != 4 && s.length() != 6) {
		answer = false;
	}
	else {
		for (int i = 0;i < s.length();i++) {
			if (s[i] > '9') {
				answer = false;
				break;
			}
		}
	}
    return answer;
}
```

