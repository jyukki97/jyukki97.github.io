# [백준]1181 단어 정렬

https://www.acmicpc.net/problem/1181

# 풀이:

배열에 들어있는 string을 길이 순서로 정렬 후

길이가 같다면, 사전순으로 정렬한다.

이 때, 중복된 문자가 있다면, 제거한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <set>
#include <string>
using namespace std;

bool com(string a, string b) {
	if (a.size() == b.size())
		return a < b;
	return a.size() < b.size();
}

int main() { 
	int n;
	cin >> n;
	string s;
	set<string, decltype(&com)> a(&com);
	for (int i = 0; i < n; i++) {
		cin >> s;
		a.insert(s);
	}
	for (auto i : a)
		cout << i << endl;
	return 0;
}
```

