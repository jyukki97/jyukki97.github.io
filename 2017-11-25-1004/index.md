# [백준]1004 어린왕자


https://www.acmicpc.net/problem/1004

# **풀이:**
1. 시작점과 도착점이 같이 원안에 있지않을 때,
   시작점, 도착점이 원 안에 있다면 카운트를 ++

# **코드:**

```C++
#include <iostream>
#include <math.h>
using namespace std;

int main(void) {
	int T;
	cin >> T;
	for (int i = 0; i < T; i++) {
		int n, x1, x2, y1, y2;
		int x[50];
		int y[50];
		int r[50];
		int count = 0;
		cin >> x1 >> y1 >> x2 >> y2 >> n;
		for (int t = 0; t < n; t++) {
			cin >> x[t] >> y[t] >> r[t];
		}
		for (int t = 0; t < n; t++) {
			if (sqrt((x1 - x[t])*(x1 - x[t]) + (y1 - y[t])*(y1 - y[t])) < r[t]) {
				if (sqrt((x2 - x[t])*(x2 - x[t]) + (y2 - y[t])*(y2 - y[t])) >= r[t])
					count++;
			}
			if (sqrt((x2 - x[t])*(x2 - x[t]) + (y2 - y[t])*(y2 - y[t])) < r[t]) {
				if (sqrt((x1 - x[t])*(x1 - x[t]) + (y1 - y[t])*(y1 - y[t])) >= r[t])
					count++;
			}
		}
		cout << count << endl;
	}
	return 0;
}
```


