# [프로그래머스]가장 긴 팰린드롬

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

앞뒤를 뒤집어도 똑같은 문자열을 팰린드롬(palindrome)이라고 합니다.
 문자열 s가 주어질 때, s의 부분문자열(Substring)중 가장 긴 팰린드롬의 길이를 return 하는 solution 함수를 완성해 주세요.



예를들면, 문자열 s가 abcdcba이면 7을 return하고 abacde이면 3을 return합니다.



# 풀이:

Manacher's algorithm 을 이용한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;
int p[5002];
int solution(string s)
{
    string a = "#";
	for (char i : s) {
		a += i;
		a += "#";
	}
	int m = 0, ed = 0, answer = 0;
	for (int i = 1; i < a.size(); i++) {
		if (i <= ed)	p[i] = min(p[m * 2 - i], ed - i);
		while (i - p[i] >= 1 && i + p[i] + 1 < a.size() && a[i - p[i] - 1] == a[i + p[i] + 1])
			p[i]++;
		if (p[i] + i > ed) {
			ed = p[i] + i;
			m = i;
		}
		answer = max(answer, p[i]);
	}
    return answer;
}
```

