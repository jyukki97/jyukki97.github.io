# [백준]14888 연산자 끼워넣기

https://www.acmicpc.net/problem/14888

# 풀이:

각 숫자를 순서대로 배열에 넣어놓는다.

\+, -, *, / 를 갯수만큼 각 숫자사이의 끼워넣어 식을 만든다.

만들 식의 값들을 배열에 저장해놓는다.

배열에 들어있는 수 중 최댓값, 최솟값을 출력한다. 



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int n, num[101], op[4];
vector<int> sumn;

void o(int a, int b) {
	if (a == n - 1) {
		sumn.push_back(b);
		return;
	}
	if (op[0] > 0) {
		op[0]--;
		o(a + 1, b + num[a + 1]);
		op[0]++;
	}
	if (op[1] > 0) {
		op[1]--;
		o(a + 1, b - num[a + 1]);
		op[1]++;
	}
	if (op[2] > 0) {
		op[2]--;
		o(a + 1, b * num[a + 1]);
		op[2]++;
	}
	if (op[3] > 0) {
		op[3]--;
		o(a + 1, b / num[a + 1]);
		op[3]++;
	}
}

int main() {
	cin >> n;
	for (int i = 0; i < n; i++)
		cin >> num[i];
	cin >> op[0] >> op[1] >> op[2] >> op[3];
	o(0, num[0]);
	sort(sumn.begin(), sumn.end());
	cout << sumn.back() << endl << sumn.front() << endl;
	return 0;
}
```

