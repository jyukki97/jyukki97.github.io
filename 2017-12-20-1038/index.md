# [백준]1038 감소하는 수


[https://www.acmicpc.net/problem/1038](http://www.acmicpc.net/problem/1038)

# **풀이:**
1. 10, 321 등 감소하는 수를 찾는 문제
2. 감소하는 수를 하나씩 만들어 가면서 카운트를 증가시킨다.
3. 카운트의 값이 제시된 N값과 일치하면 출력한다.
4. 제시된 N값이 9876543210의 위치인 1022 보다 크다면 -1을 출력한다.

# **코드:**

```C++
#include <iostream>
#include <vector>
using namespace std;
vector<int> a;
int main(void) {
	int n;
	int cnt = 11;
	cin >> n;
	if (n < 11) {
		cout << n << endl;
	}
	else if (n > 1022)
		cout << "-1" << endl;
	else {
		a.push_back(0);
		a.push_back(2);
		while (cnt != n) {
			a[0]++;
			for (int i = 0; i < a.size() - 1; i++) {
				if (a[i] >= a[i + 1]) {
					a[i] = 0;
					a[i + 1]++;
					i = -1;
				}
				if (a[i + 1] > 9) {
					a[i + 1] = 0;
					if (i + 1 == a.size() - 1) {
						a.push_back(1);
						i = -1;
					}
					else
						a[i + 2]++;
				}
			}
			cnt++;
		}
		for (int i = a.size() - 1; i >= 0; i--) {
			cout << a[i];
		}
		cout << endl;
	}
	return 0;
}
```

