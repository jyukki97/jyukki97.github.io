# [백준]17273 카드 공장 (Small)


https://www.acmicpc.net/problem/17273

# 풀이:

카드 1장을



공장장의 말에 따라 뒤집는다.



마지막 명령이 끝났을 때, 카드의 윗면에 그려진 숫자를 출력한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
using namespace std;

int main() {
	int n, m, a, b, d;
	cin >> n >> m >> a >> b;
	for (n = a; m--;) {
		cin >> d;
		if (n <= d) n = n == a ? b : a;
	}
	cout << n << endl;
}
```
