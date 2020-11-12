# [백준]17265 나의 인생에는 수학과 함께

https://www.acmicpc.net/problem/17265

# 풀이:

최단 거리이므로 오른쪽과 아래쪽으로만 이동한다.



현재 위치가 연산자라면,



이전까지 연산해왔던 값을 x라고 하자

연잔자를 ㅁ 라고 하고,

다음 이동할 곳의 숫자를 y라고 하자.



현재 위치의 연산자를 이용하여 x ㅁ y 를 연산한 후 다음 숫자로 이동한다.



현재 위치가 숫자라면,  현재 위치가 학교인지 판단 후

학교가 아니라면 오른쪽 또는 아래로 이동한다.



학교라면 현재까지 연산해왔던 값이 지금 저장해 놓은 최댓값보다 크다면 교체한다.

또한 현재까지 연산해왔던 값이 지금 저장해 놓은 최솟값보다 작다면 교체한다.





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t, s = -4000, f = 4000, b[8][8]; char c[8][8];
void P(int x, int y, int z) {
	if (x == n - 1 && y == n - 1) {
		s = s < z ? z : s;
		f = f > z ? z : f;
		return;
	}
	for (int u = 0; u < 2; u++) {
		int q = x + u, w = y - u + 1;
		if (q >= n || w >= n) continue;
		if (!b[q][w]) {
			b[q][w] = 1;
			if (c[x][y] == '+')	P(q, w, z + c[q][w] - '0');
			else if (c[x][y] == '-')  P(q, w, z - c[q][w] + '0');
			else if (c[x][y] == '*')  P(q, w, z * (c[q][w] - '0'));
			else	P(q, w, z);
			b[q][w] = 0;
		}
	}
}
int main() {
	cin >> n;
	for (; i < n; i++)
		for (t = 0; t < n; t++)
			cin >> c[i][t];
	P(0, 0, c[0][0] - '0');
	cout << s << " " << f <<  endl;
}
```

