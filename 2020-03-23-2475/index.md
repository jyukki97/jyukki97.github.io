# [백준]2475 검증수

https://www.acmicpc.net/problem/2475

# 풀이:

고유번호의 각 자릿수를 제곱한 값을 더한 후 10으로 나눈 나머지를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int x, i, s = 0;
int main() {
	for (i = 0; i < 5; i++) {
		cin >> x;
		s += x * x;
	}
	cout << s % 10 << endl;
}
```

