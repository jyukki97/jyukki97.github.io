# [프로그래머스]JadenCase 문자열 만들기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.



# 풀이:

[[C++\]대소문자, 숫자 구분함수 ](http://jyukki97.github.io/learn/2020-01-02-distinguishstring/) 참고

모든 단어의 첫 문자가 대문자가 아니라면 대문자로 바꾼다.

첫 문자가 아니라면 소문자로 바꾼다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

string solution(string s) {
    int c = 0;
	for (int i = 0;i < s.size();i++) {
		if (!c) {
			s[i] = toupper(s[i]);
			c++;
		}
		else s[i] = tolower(s[i]);
		if (s[i] == ' ')	c = 0;
	}
    return s;
}
```

