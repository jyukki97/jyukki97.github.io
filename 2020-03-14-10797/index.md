# [백준]10797 10부제

https://www.acmicpc.net/problem/10797

# 풀이:

날짜의 일의 자리 숫자와 자동차의 일의 자리 숫자가 같다면 차량의 대수를 +1 해준다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, s = 0;
int main() {
	cin >> n;
	for (i = 0; i < 5; i++) {
		cin >> m;
		if (n == m)	s++;
	}
	cout << s << endl;
}
```

