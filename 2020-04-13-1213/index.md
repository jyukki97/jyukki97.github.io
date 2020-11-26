# [백준]1213 팰린드롬 만들기

https://www.acmicpc.net/problem/1213

# 풀이:

주어진 문자열에서 알파벳이 각각 몇개 들어있는지 저장한다.

A~Z 까지 갯수를 확인한 후

앞뒤로 하나씩 넣는다.

홀수개인 알파벳이 2개 이상 이라면, 문자열을 만들 수 없으므로  "I'm Sorry Hansoo"를 출력한다.

문자열의 길이가 홀수라면, 가운데에 1개남은 글자를 넣어준다. 



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int i, c = -1, f, t, b[26];  string s;
int main() {
	cin >> s;
	for (; i < s.size(); i++) b[s[i] - 65]++;
	for (i = 0; !f && i < 26; i++)
		if (b[i]) {
			while (b[i] > 1) 
                s[t] = i + 65, s[s.size() - t - 1] = i + 65, t++, b[i] -= 2;
			if (b[i] % 2) f = c != -1, c = i;
		}
	if (s.size() % 2)	s[s.size() / 2] = c + 65;
	if (f)	cout << "I'm Sorry Hansoo" << endl;
	else cout << s << endl;
}
```

