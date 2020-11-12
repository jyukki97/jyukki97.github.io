# [백준]1699 제곱수의 합


[https://www.acmicpc.net/problem/1699](http://www.acmicpc.net/problem/1699)

# **풀이:**
1. q[i] 는 i 일 때 제곱수로 나타낼 수 있는 최소의 경우의 수
2. n 이 i + t^2 으로 나타내 질 때, 최소의 경우의 수를 찾음 

# **코드:**

```C++
#include <iostream>
#include <math.h>
int q[100002] = { 0 };
using namespace std;
int main(void) {
	int n,a;
	cin >> n;
	a = sqrt(n);
	for (int i = 1; i <= n; i++)
	{
		q[i] = 10001;
		for (int t = 1; t <= a; t++)
		{
			if (i == t*t)
				q[i] = 1;
		}
	}
	for (int i = 1; i <= n; i++)
	{
		for (int t = 1; t <= a; t++)
		{
			if (i + (t*t) <= n && q[i + (t*t)] > q[i] + 1)
				q[i + (t*t)] = q[i] + 1;
		}
	}
	cout << q[n] << endl;
}
```


