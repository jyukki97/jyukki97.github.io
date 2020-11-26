# [백준]10799 쇠막대기

https://www.acmicpc.net/problem/10799

# 풀이:

[[프로그래머스\]쇠막대기](https://jyukki97.github.io/blog/2020-01-17-ironbar/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <stack>
using namespace std;
int n, i, b = 0; stack<char> a;	string s;
int main() {
	cin >> s;
	for (i = 0; i < s.size() - 1; i++)
		if (s[i] == '(')
			if (s[i + 1] == ')')	b += a.size(), i++;
			else a.push(s[i]);
		else	a.pop(), b++;
	cout << b + 1 << endl;
}
```

