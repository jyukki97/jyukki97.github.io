# [백준]14612 김식당


https://www.acmicpc.net/problem/14612

# 풀이:

order를 <주문시간, 테이블번호> 를 변수로 하는 vector에 차곡차곡 쌓는다.



각 주문이 끝난 후 vector의 들어있는 테이블 번호를 순서대로 출력한다.



만약 sort가 들어왔다면, 주문시간을 기준으로 vector를 정렬한다



만약 complete가 들어왔다면,  완성된 테이블 번호를 vector에서 제거한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
	int n, m, a, b, i;
	vector<pair<int, int>> v;
	cin >> n >> m;
	while (n--) {
		string s;
		cin >> s;
		if (s == "order") {
			cin >> a >> b;
			v.push_back({ b,a });
		}
		else if (s == "sort") {
			sort(v.begin(), v.end());
		}
		else {
			cin >> a;
			for (i = 0; i < v.size(); i++) {
				if (v[i].second == a) {
					v.erase(v.begin() + i);
					break;
				}
			}
		}
		if (v.empty()) {
			cout << "sleep" << endl;
		}
		else {
			for (i = 0; i < v.size(); i++) {
				cout << v[i].second << " ";
			}
			cout << endl;
		}
	}
}
```
