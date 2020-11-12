# 3067 Coins

[https://www.acmicpc.net/problem/3067](http://www.acmicpc.net/problem/3067)

#### **풀이:**
1. 출처의 문제와 같으므로 출처를 참고.

#### **코드:**

```
#include <iostream>
using namespace std;
int main(void)
{
	int T, a, num;
	cin >> T;
	for (int y = 0; y < T; y++) {
		int coin[10001] = { 0 };
		cin >> a;
		int *q = new int[a];
		for (int i = 0; i < a; i++)
			cin >> q[i];
		cin >> num;
		for (int i = 0; i <= num; i++) {
			if (i%q[0] == 0)
				coin[i]++;
		}
		for (int i = 1; i < a; i++) {
			for (int t = q[i]; t <= num; t++)
				coin[t] += coin[t - q[i]];
		}
		cout << coin[num] << endl;
	}
	return 0;
}

```

#### **출처 : 2293 동전1 **
[https://jyukki97.github.io/2293](https://jyukki97.github.io/2293)
