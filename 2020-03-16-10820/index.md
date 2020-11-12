# [백준]10820 문자열 분석

https://www.acmicpc.net/problem/10820

# 풀이:

[[C++\]대소문자, 숫자 구분함수 ](https://jyukki97.github.io/learn/2020-01-02-distinguishstring/) 참고



###### 따로 종료 조건이 없으므로 EOF 처리를 해주자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;
int main() {
	string s;
	while (getline(cin, s)) {
		int a = 0, b = 0, c = 0, d = 0;
		for (char i : s)
			if (islower(i)) a++;
			else if (isupper(i)) b++;
			else if (isdigit(i)) c++;
			else d++;
		printf("%d %d %d %d\n", a, b, c, d);
	}
}
```

