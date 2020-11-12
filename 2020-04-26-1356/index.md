# [백준]1356 유진수

https://www.acmicpc.net/problem/1356

# 풀이:

1의 자릿수 == 10의 자릿수\*...*n자릿수

1의 자릿수 * 10의 자릿수 == 100의 자릿수 \*...*n자릿수

.

.

.

1의 자릿수\*...*n-1자릿수 == n 자릿수



중 앞의 값과 뒤의 값이 같은 것이 하나라도 있다면, YES를

하나도 없다면 NO를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n = 1, m = 1, i, t, f; string s;
int main() {
	cin >> s;
	for (i = 1; i < s.size(); f += n == m, n = 1, m = 1, i++) {
		for (t = 0; t < i; t++) n *= (s[t] - 48);
		for (t = i; t < s.size(); t++) m *= (s[t] - 48);
	}
	printf("%s", f ? "YES" : "NO");
}
```

