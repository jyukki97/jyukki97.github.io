# 2688 줄어들지 않아

[https://www.acmicpc.net/problem/2688](http://www.acmicpc.net/problem/2688)

#### **풀이:**
1. a[t][y] : t + 1 개의 자릿수에서의 줄어들지 않는 수의 갯수
2. a[t][y] = a[t][y - 1] + a[t - 1][y]
3. 앞자리의 갯수가 1 증가할 때 마다 이전 자릿수의 개수를 더해가는 방식으로 구한다.
4. 최종 자릿수 9가되면 모든 수가 누적되어 있으므로 출력한다.

#### **코드:**

```
#include <iostream>
using namespace std;
long long a[65][10] = { 1,2,3,4,5,6,7,8,9,10,0 };
int main(void) {
	int T, n;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> n;
		for (int t = 1; t < n; t++) {
			a[t][0] = 1;
			for (int y = 1; y < 10; y++) {
				a[t][y] = a[t][y - 1] + a[t - 1][y];
			}
		}
		cout << a[n - 1][9] << endl;
	}
	return 0;
}
```

#### **사간 초과 풀이:**
1. 처음 풀이를 할 때 저번 1038 감소하는 수를 푸는 것처럼
2. 하나하나 만들어 가면서 카운트를 하려 했으나 시간초과가 난다.


#### **시간 초과 코드:**

```
#include <iostream>
#include <vector>
using namespace std;
vector<int> a;
int main(void) {
	int T, n;
	cin >> T;
	for (int i = 0; i < T; i++) {
		int cnt = 1;
		cin >> n;
		for (int t = 0; t < n; t++)
			a.push_back(0);
		while (a[n - 1] < 10) {
			a[0]++;
			for (int t = 0; t < n - 1; t++) {
				if (a[t] == 10) {
					a[t + 1]++;
					a[t] = 0;
				}
				if (a[t] > a[t + 1]) {
					a[t + 1]++;
					a[t] = 0;
				}
			}
			cnt++;
		}
		cout << cnt - 1 << endl;
	}
	return 0;
}
```
