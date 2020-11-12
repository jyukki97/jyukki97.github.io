# [백준]2089 -2진수

https://www.acmicpc.net/problem/2089

# 풀이:

2진수를 구하듯이 구한다.



\-2	13

​		-6	...	1

​		 3	...	0

​		-1	...	1

​		 1	...	1



13 = 11101(-2)





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n;
void G(int x) {
	if (!x)	return;
	G(x % -2 < 0 ? (x / -2) + 1 : x / -2);
	if (x % -2 < 0) cout << -1 * (x % -2);
	else cout << x % -2;
}
int main() {
	cin >> n;
	G(n);
	if (!n)	cout << 0;
	cout << endl;
}
```

