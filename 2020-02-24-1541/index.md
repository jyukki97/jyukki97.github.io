# [백준]1541 잃어버린 괄호

https://www.acmicpc.net/problem/1541

# 풀이:

문자열을 하나씩 확인한다.

\+ 라면, 괄호를 치지않는다.

\- 라면, 괄호를 친다.



즉, -가 나오면 시작괄호를 치고, 다음 -가 나오면, 끝나는 괄호가 된다.

ex) 45 + 55 - 65 + 45 - 67 + 67

= 45 + 55 - (65 + 45) - (67 + 67)



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
	string s;
	vector<int> a;
	int n = 0;
	cin >> s;
	a.push_back(stoi(s));
	for (int i = 0; i < s.size(); i++)
		if (s[i] == '+')
			a.back() += stoi(s.substr(i + 1, 6));
		else if (s[i] == '-') {
			n -= a.back();
			a.push_back(stoi(s.substr(i + 1, 6)));
		}
	cout << n + (a[0] * 2) - a.back() << endl;
	return 0;
}
```

