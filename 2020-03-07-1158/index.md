# [백준]1158 요세푸스 문제

https://www.acmicpc.net/problem/1158

# 풀이:

K번째 사람을 출력한다.

K번째 사람을 배열에서 삭제한다.

삭제한 지점을 기준으로 K번째 사람을 출력한다.

반복한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int N, K, c;
int main() {
	cin >> N >> K;
	vector<int> a;
	for (int i = 1; i <= N; i++)	a.push_back(i);
	c = K - 1;
	cout << "<";
	while (a.size() != 1) {
		if (c >= a.size())	c %= a.size();
		cout << a[c] << ", ";
		a.erase(a.begin() + c);
		c += K - 1;
	}
	cout << a[0] << ">" << endl;
}
```

