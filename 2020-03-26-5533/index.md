# [백준]5533 유니크

https://www.acmicpc.net/problem/5533

# 풀이:

각 플레이어가 3번의 게임에서 얻은 총 점수를 입력으로 주어진 순서대로 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int n, a[201][3], i, t, b[3][101], s;
int main() {
	cin >> n;
	for (i = 0; i < n; i++) for (t = 0; t < 3; b[t][a[i][t++]]++) cin >> a[i][t];
	for (i = 0; i < n; i++, s = 0) {
		for (t = 0; t < 3; t++) s += b[t][a[i][t]] > 1 ? 0 : a[i][t];
		cout << s << endl;
	}
}
```

