# [백준]1453 피시방 알바

https://www.acmicpc.net/problem/1453

# 풀이:

거절당하는 사람의 수를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, s = 0, a[101];
int main() {
	cin >> n;
	while (n--) {
		cin >> m;
		a[m]?s++:a[m]++;
	}
	cout << s << endl;
}
```

