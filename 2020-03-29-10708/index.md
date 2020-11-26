# [백준]10708 크리스마스 파티

https://www.acmicpc.net/problem/10708

# 풀이:

게임을 진행한다.

적은 대상이 타겟이라면 적은 사람을 +1 타겟이 아니라면 타겟인 사람을 +1 해준다.

게임 이 끝난 후 각각의 친구들이 얻은 합계 점수를 각각 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int  n, m, i, t, c, a[102], b[102];
int main() {
	cin >> n >> m;
	for (; i < m; i++) cin >> a[i];
	for (i = 0; i < m; i++)
		for (t = 0; t < n; b[c==a[i]?t:a[i]-1]++,t++)
			cin >> c;
	for (i = 0; i < n; i++)		cout << b[i] << endl;
}
```

