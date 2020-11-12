# [백준]10996 별 찍기 - 21

https://www.acmicpc.net/problem/10996

# 풀이:

지그제그로 n번 별을 찍는다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t;
int main() {
	cin >> n;
	for (i = 0; i < n * 2; i++) {	
		for (t = 0; t < n / 2 + (i % 2 ? 0 : n % 2); t++)	
            printf("%s", i % 2 ? " *" : "* ");
		cout << endl;
	}
}
```

