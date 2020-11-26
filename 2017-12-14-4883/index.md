# [백준]4883 삼각 그래프


[https://www.acmicpc.net/problem/4883](http://www.acmicpc.net/problem/4883)

# **풀이:**
1. N X 3 행렬에서 맨 위 중앙에서 출발하여 맨 아래 중앙까지 가는 경로 중 가장 최소 비용을 찾는 문제
2. 각 i행의 1,2,3번째 열의 각각 최소비용은 i-1 번째 행에서의 최소 비용을 더해준 값이다.
3. 맨 마지막 행의  2번째 열을 출력한다.
4. 0이 출력되면 끝나므로 if문으로 while 문을 빠져나갈 수 있게한다.
5. 하나의 테스트케이스마다 숫자를 출력해야하므로 count 값을 각 케이스마다 ++해준다.

# **코드:**

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[100005][3], b[100005][3];
int main(void) {
	int count = 1;
	while (true) {
		int n, temp, temp2;
		cin >> n;
		if (n == 0)
			break;
		for (int i = 0; i < n; i++) {
			for (int t = 0; t < 3; t++) {
				cin >> a[i][t];
				b[i][t] = a[i][t];
			}
		}
		b[0][2] += b[0][1];
		b[1][0] += b[0][1];
		b[1][1] += min(min(b[0][1],b[1][0]), b[0][2]);
		b[1][2] += min(min(b[1][1], b[0][1]), b[0][2]);
		for (int i = 2; i < n; i++) {
			for (int t = 0; t < 3; t++) {
				if (t == 0)
					b[i][t] += min(b[i - 1][t], b[i - 1][t + 1]);
				else if (t == 1)
					b[i][t] += min(min(b[i - 1][t], b[i - 1][t + 1]), min(b[i - 1][t - 1], b[i][t - 1]));
				else if (t == 2)
					b[i][t] += min(min(b[i - 1][t - 1], b[i - 1][t]), b[i][t - 1]);
			}
		}
		cout << count << ". " << b[n - 1][1] << endl;
		count++;
	}
	return 0;
}
```


