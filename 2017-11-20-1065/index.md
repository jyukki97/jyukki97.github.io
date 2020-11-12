# [백준]1065 한수


https://www.acmicpc.net/problem/1065

# 풀이:

한수이면 카운트를 ++ 하는 함수를 만듦

# 코드:

사용언어 : c++

```c++
#include <iostream>
using namespace std;

int hannum(int n, int c) {
	int b = (n % 1000) / 100;
	int d = ((n % 1000) % 100) / 10;
	int f = ((n % 1000) % 100) % 10;
	if (n > 99) {
		if ((b - d == d - f) && n != 1000)
			c++;
	}
	else
		c++;
	
	if (n == 1)
		return c;
	else
		return hannum(n - 1, c);
}

int main(void) {
	int a;
	cin >> a;

	cout << hannum(a, 0);

	return 0;
}
```


