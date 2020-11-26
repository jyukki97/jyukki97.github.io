# [백준]5523 경기 결과

https://www.acmicpc.net/problem/5523

# 풀이:

각 경기마다 a가 이겼다면 a++ 를

b가 이겼다면 b++를 해준다.

모든 경기가 끝난 후 a와 b값을 출력해준다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, a = 0, b = 0, x, y;
int main() {
	cin >> n;
	while (n--) {
		cin >> x >> y;
		if (x > y)	a++;
		if (x < y)	b++;
	}
	cout << a << " " << b << endl;
}
```

