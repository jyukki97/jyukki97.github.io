# [백준]2822 점수 계산

https://www.acmicpc.net/problem/2822

# 풀이:

첫째 줄에 참가자의 총점을 출력한다. 

둘째 줄에는 어떤 문제가 최종 점수에 포함되는지를 공백으로 구분하여 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int n, m, k, s = 0;
int main() {
	vector<pair<int, int>>a;
	for (int i = 1; i < 9; i++) {
		cin >> n;
		if (i >= 6) {
			m = 151;
			for (int t = 0; t < 5; t++) if (a[t].first < m) m = a[t].first, k = t;
			if (a[k].first < n) a.erase(a.begin() + k), a.push_back({ n,i });
		}
		else a.push_back({ n, i });
	}
	for (auto i : a)	s += i.first;
	cout << s << endl;
	for (auto i : a)	cout << i.second << " ";
	cout << endl;
}
```

