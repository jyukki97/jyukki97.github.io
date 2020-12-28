# [백준]17264 I AM IRONMAN


https://www.acmicpc.net/problem/17264

# 풀이:

이길 수 있는 사람을 set에 모아놓는다.



만약 만난 사람이 set에 존재한다면, score에 획득 점수를 더해준다.



만약 만난 사람이 set에 존재하지 않는다면, score에 떨어지는 점수를 빼준다.



만약 score가  IRON 티어에서 벗어나기 위한 점수보다 높아진다면, 

"I AM NOT IRONMAN!!" 을 출력한다.



모든 플레이어를 만났음에도  IRON 티어에서 벗어나기 위한 점수보다 낮다면,

"I AM IRONMAN!!"을 출력한다.



score값은 음수가 될 수 없으므로 주의하자!!!



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <set>
using namespace std;

int main() {
	int n, p, w, l, g, c = 0;
	set<string> s;
	string t, h;
	for (cin >> n >> p >> w >> l >> g; p--;s.insert(h=="W"?t:"")) cin >> t >> h;
	for (; n--; c = c < 0 ? 0 : c) {
		cin >> t;
		c += s.find(t) != s.end() ? w : -l;
		if (c >= g) cout << "I AM NOT IRONMAN!!" << endl, exit(0);
	}
	cout << "I AM IRONMAN!!" << endl;
}
```
