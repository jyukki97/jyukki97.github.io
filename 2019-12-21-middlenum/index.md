# [프로그래머스]가운데 글자 가져오기

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 문자열 s의 가운데 글자를 리턴한다.
2. 만약 문자열 s의 길이가 짝수라면 가운데 두 글자를 반환한다

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(string s) {
    string answer;
    if (s.length() % 2 == 0) {
	    answer = s[s.length() / 2 - 1];
		answer += s[s.length() / 2];
	}
	else {
		answer = s[s.length() / 2];
	}
    return answer;
}
```

