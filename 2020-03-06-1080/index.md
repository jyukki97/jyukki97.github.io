# [백준]1080 행렬

https://www.acmicpc.net/problem/1080

# 풀이:

(0, 0) 부터 하나씩 비교해 나간다.

만약 A 와 B 의 숫자가 다르다면, 현재 위치부터 3 * 3 전체를 반전시킨다.

반전 시켰다면, 뒤집은 횟수를 +1 해준다.



순환이 끝난 후 행렬 A 와 B 가 다르다면 -1을 같다면 뒤집은 횟수를 출력해준다.   



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int N, M, c = 0, i, t, u, y;
int main() {
	cin >> N >> M;
	vector<string> a(N), b(N);
	for (i = 0; i < N; i++)
		cin >> a[i];
	for (i = 0; i < N; i++)
		cin >> b[i];
	for (i = 0; i < N - 2; i++)
		for (t = 0; t < M - 2; t++)
			if (a[i][t] != b[i][t]) {
				c++;
				for (y = 0; y < 3; y++)
					for (u = 0; u < 3; u++)
						a[i + y][t + u] = '1' - a[i + y][t + u] + '0';
			}
	for (i = 0; i < N; i++)
		if (a[i] != b[i])	c = -1;
	cout << c << endl;
}
```

