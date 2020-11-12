# [백준]5063 TGN

https://www.acmicpc.net/problem/5063

# 풀이:

광고를 했을 때의 수익 - 광고 비용 이 광고를 했을 떄 얻을 수 있는 순이익이다.

즉,  광고를 하지않았을 때의 수익과 광고를 했을 때 얻을 수 있는 순 이익을 비교하여,

해야 하면 "advertise", 하지 않아야 하면 "do not advertise", 광고를 해도 수익이 차이가 없다면 "does not matter"를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int T, k, n, m;
int main() {
	cin >> T;
	while (T--) {
		cin >> k >> n >> m;
		n -= m;
		if (k == n)	cout << "does not matter" << endl;
		else if (k < n) cout << "advertise" << endl;
		else cout << "do not advertise" << endl;
	}
}
```

