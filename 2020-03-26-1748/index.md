# [백준]1748 수 이어 쓰기 1

https://www.acmicpc.net/problem/1748

# 풀이:

1 ~ N 까지의 1의 자릿수의 갯수

\+ 1 ~ N 까지의 10의 자릿수의 갯수

.

.

.

\+ 1 ~ N 까지의 N의 최대 자릿수의 갯수



= 1 ~ N 까지의 수를 이어서 썻을 때의 자릿수



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int n, a, b = 1;
int main() {
	for (cin >> n; n > b; b *= 10)	a += n - b + 1;
	cout << a << endl;
}
```

