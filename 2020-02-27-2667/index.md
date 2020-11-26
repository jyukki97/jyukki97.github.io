# [백준]2667 단지번호붙이기

https://www.acmicpc.net/problem/2667

# 풀이:

전체를 순회한다.



만약 집이있는 곳 ( 배열에 1인 곳 ) 을 찾았다면, 연결된 모든 단지를 찾아 단지 크기를 배열에 저장한다.



순회가 끝났다면, 배열의 사이즈 (총 단지수) 를 출력한다.



그 후 단지내 집의 수를 오름차순으로 정렬하여 출력하여야하므로



배열을 정렬한 후 배열의 원소를 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;
int n;
bool b[26][26];
vector<string> a;
vector<int> c;
void num(int x, int y) {
	b[x][y] = true;
	c.back()++;
	if (x + 1 < n && a[x + 1][y] == '1' && !b[x + 1][y])
		num(x + 1, y);
	if (y + 1 < n && a[x][y + 1] == '1' && !b[x][y + 1])
		num(x, y + 1);
	if (x - 1 >= 0 && a[x - 1][y] == '1' && !b[x - 1][y])
		num(x - 1, y);
	if (y - 1 >= 0 && a[x][y - 1] == '1' && !b[x][y - 1])
		num(x, y - 1);
}
int main() {
	cin >> n;
	a.resize(n);
	for (int i = 0; i < n; i++)
		cin >> a[i];
	for (int i = 0; i < n; i++)
		for (int t = 0; t < n; t++)
			if (a[i][t] == '1' && !b[i][t]) {
				c.push_back(0);
				num(i, t);
			}
	cout << c.size() << endl;
	sort(c.begin(), c.end());
	for (int i : c)
		cout << i << endl;
}
```

