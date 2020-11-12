# [백준]1051 숫자 정사각형

https://www.acmicpc.net/problem/1051

# 풀이:

N, M 중 더 작은 값이 정사각형의 한 변의 길이의 최댓값이 된다.

최댓값을 1씩 줄여 가면서, 만들 수 있는 정사각형이 있는지 확인한다.

만들 수 있다면, 반복을 중지하고, 변을 제곱한 넓이를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int N, M, b, c = 1;
int main(void) {
	cin >> N >> M;
	vector<string> a(N);
	for (int i = 0; i < N; i++)
			cin >> a[i];
	b = N > M ? M : N;
	while (c && --b) {
		for (int i = 0; i < N - b; i++)
			for (int t = 0; t < M - b; t++)
				if (a[i][t + b] == a[i][t] && a[i + b][t] == a[i][t] && a[i + b][t + b] == a[i][t])
					c = 0;
	}
	cout << (b + 1) * (b + 1) << endl;
}
```

