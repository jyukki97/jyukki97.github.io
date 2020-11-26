# [백준]1525 퍼즐

https://www.acmicpc.net/problem/1525

# 풀이:

|  0   |  1   |  2   |
| :--: | :--: | :--: |
|  3   |  4   |  5   |
|  6   |  7   |  8   |

이렇게 퍼즐이 배열되어 있다고 가정하자.

우리는 이것을 012345678 -> int형으로 바꿔 생각하도록 하자.

이 때, 0이 맨 앞에 나올 경우 무시되므로 0 -> 9 로 바꿔서

912345678 로 나타내도록 하자.



우리가 찾아야 하는 퍼즐의 상태는 123456789 이다.



주어진 퍼즐에서 9를 오른쪽, 왼쪽, 위, 아래 로 옮기면서, 123456789가 되는 지점 까지 BFS를 돌린다.



만약 모든 종류의 퍼즐을 돌았음에도 123456789를 못찾았다면, -1을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
#include <queue>
#include <map>
using namespace std;
int i, t, a, w, f;
int main() {
	map<int, int> m;
	for (; i < 9; w = w ? w : 9, a = a * 10 + w, i++)	cin >> w;
	queue<int> q;
	q.push(a), m[a] = 1;
	for (i = 0;!q.empty(); i++) {
		queue<int> p;
		while (!q.empty()) {
			string s = to_string(q.front());
			if (q.front() == 123456789) {
				f = 1;
				break;
			}
			w = s.find('9');
			if (w < 6) {
				swap(s[w], s[w + 3]);
				if (!m.count(stoi(s))) p.push(stoi(s)), m[stoi(s)] = 1;
				swap(s[w], s[w + 3]);
			}
			if (w > 2) {
				swap(s[w], s[w - 3]);
				if (!m.count(stoi(s))) p.push(stoi(s)), m[stoi(s)] = 1;
				swap(s[w], s[w - 3]);
			}
			if (w % 3 < 2) {
				swap(s[w], s[w + 1]);
				if (!m.count(stoi(s))) p.push(stoi(s)), m[stoi(s)] = 1;
				swap(s[w], s[w + 1]);
			}
			if (w % 3 > 0) {
				swap(s[w], s[w - 1]);
				if (!m.count(stoi(s))) p.push(stoi(s)), m[stoi(s)] = 1;
				swap(s[w], s[w - 1]);
			}
			q.pop();
		}
		q = p;
		if (f) break;
	}
	printf("%d", f ? i : -1);
}
```

