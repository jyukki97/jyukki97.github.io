# [백준]10833 사과

https://www.acmicpc.net/problem/10833

# 풀이:

배정된 사과 수를 학생수로 나눈 나머지를 모두 더해 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int N, a, b, c = 0;
int main() {
	cin >> N;
	while (N--) {
		cin >> a >> b;
		c += b % a;
	}
	cout << c << endl;
}
```

