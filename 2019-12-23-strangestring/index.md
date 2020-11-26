# [프로그래머스]이상한 문자 만들기

[https://programmers.co.kr](https://programmers.co.kr)

# **문제:**

문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

# **풀이:**
1. 문자열 전체의 짝/홀수 인덱스가 아니라 각 단어 기준이므로 주의한다.
2. 공백문자가 하나가 아닐 수도 있으므로 주의한다.
3. 공백문자를 기준으로 단어를 나누므로, 공백문자가 나왔을 경우 카운트를 초기화하는 식으로 문자열을 나눈다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(string s) {
	int c = 0;
	for (int i = 0;i < s.size();i++) {
		if (s[i] == ' ')
			c = 0;
		else {
			if (c % 2 == 0)
				s[i] = toupper(s[i]);
			else if (c % 2 == 1)
				s[i] = tolower(s[i]);
			c++;
		}
	}
    return s;
}
```

