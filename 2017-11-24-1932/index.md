# [백준]1932 숫자삼각형


https://www.acmicpc.net/problem/1932

# **풀이:**
1. 첫 줄부터 밑에줄까지 내려가면서 값을 더해감
2. 더한 값중 제일 큰 값을 찾음

# **코드:**

```c++
#include <iostream>
using namespace std;

int q[501][501];
int good[501][501];

int main(void)
{
	int num;
	int big = 0;
	cin >> num;
	for (int i = 0; i < num; i++){
		for (int t = 0; t < i + 1; t++){
			cin >> q[i][t];
		}
	}
	good[0][0] = q[0][0];
	for (int i = 1; i < num; i++)
	{
		for (int t = 0; t < i+1; t++){
			if(t==0)
				good[i][t] = good[i - 1][t] + q[i][t];
			else if (i == t)
				good[i][t] = good[i - 1][t - 1] + q[i][t];
			else
			{
				if (good[i - 1][t - 1] > good[i - 1][t])
					good[i][t] = good[i - 1][t - 1] + q[i][t];
				else
					good[i][t] = good[i - 1][t] + q[i][t];
			}
		}
	}
	for (int i = 0; i < num; i++)
	{
		if (good[num - 1][i] > big)
			big = good[num - 1][i];
	}
	cout << big << endl;
	return 0;
}
```


