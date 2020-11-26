# [백준]10995 별 찍기 - 20

https://www.acmicpc.net/problem/10995

# 풀이:

주어진 규칙대로 별을 찍는다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t;
int main() {
	cin >> n;
	for (i = 0; i < n; i++) {
		for (t = 0; t < n; t++) printf("%s", i % 2 ? " *" : "* ");
		printf("\n");
	}
}
```

