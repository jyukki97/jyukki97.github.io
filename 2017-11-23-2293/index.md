# [백준]2293 동전1


https://www.acmicpc.net/problem/2293

# **풀이:**
1. 첫번째 동전부터 경우의 수를 더해감.

# **코드:**

```c++
#include <iostream>
using namespace std;

int coin[10001] = { 0 };

int main(void)
{
	int a;
	int num;
	cin >> a;
	cin >> num;
	int *q = new int[a];
	for (int i = 0; i < a; i++){
		cin >> q[i];
	}
	for (int i = 0; i <= num; i++){
		if (i%q[0] == 0)
			coin[i]++;
	}
	for (int i = 1; i < a; i++){
		for (int t = q[i]; t <= num; t++){
			coin[t] += coin[t - q[i]];
		}
	}
	cout << coin[num] << endl;
	return 0;
}
```


