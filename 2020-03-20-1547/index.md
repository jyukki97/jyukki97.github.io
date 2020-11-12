# [백준]1547 공

https://www.acmicpc.net/problem/1547

# 풀이:

주어진 입력에 따라 컵의 위치를 바꾼다.

입력이 끝난 후 공이 들어있는 컵의 번호를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, x, y, a[4] = { 0,1 };
int main() {
	cin >> n;
	while (n--) {
		cin >> x >> y;
		swap(a[x], a[y]);
	}
	for (int i = 1; i < 4; i++)	if (a[i])	cout << i << endl;
}
```

