# [백준]1915 가장 큰 정사각형

https://www.acmicpc.net/problem/1915

# 풀이:

b\[i][t] : i , t 가 오른쪽 아래 꼭짓점인 정사각형의 한 변의 길이

i, t가 0이라면, 정사각형을 만들 수 없으므로 0

i, t 의 수가 1이라면,

b\[i][t] = (b\[i - 1][t], b\[i][t - 1], b\[i - 1][t - 1] 의 최솟값) + 1



넓이 이므로 b\[i][t] 중 가장 큰 값을 제곱하여 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, t, a, b[1002][1002], s = 0;
int main() {
	cin >> n >> m;
	for (i = 0; i < n; i++)	
		for (t = 0; t < m; t++) {
			scanf_s("%1d",&a);
			if (a) {
				if (i && t) {
				  b[i][t] = b[i - 1][t] > b[i][t - 1] ? b[i][t - 1] : b[i - 1][t];
				  b[i][t] = b[i][t] > b[i - 1][t - 1] ? b[i - 1][t - 1] : b[i][t];
				}
				b[i][t]++;
				s = s > b[i][t] ? s : b[i][t];
			}
		}
	cout << s * s << endl;
}
```

