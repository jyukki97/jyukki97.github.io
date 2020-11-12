# [백준]17176 암호해독기

https://www.acmicpc.net/problem/17176

# 풀이:

암호의 쓰인 알파벳들을 저장한다.

평문을 살펴보며 암호에 쓰였는지 확인한다.

암호의 없는 알파벳이 나온다면, n을 아니라면 y를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, b, i, s, a[53];
int main() {
	cin >> n;
	for (i = 0; i <= n; i++) { cin >> m; a[m]++; }
	for (i = 0; i < n; i++) {
		s = getchar();
		s -= s > 96 ? 70 : s > 64 ? 64 : 32;
		if (a[s])	a[s]--;
		else 	b = 1;
	}
	printf("%s", b ? "n" : "y");
}
```

