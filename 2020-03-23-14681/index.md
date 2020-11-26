# [백준]14681 사분면 고르기

https://www.acmicpc.net/problem/14681

# 풀이:

점 (x, y)의 사분면 번호를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int x, y;
int main() {
	cin >> x >> y;
	if (x > 0 && y > 0)	cout << "1" << endl;
	if (x < 0 && y > 0)	cout << "2" << endl;
	if (x < 0 && y < 0)	cout << "3" << endl;
	if (x > 0 && y < 0)	cout << "4" << endl;
}
```

