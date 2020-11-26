# [백준]2864 5와 6의 차이

https://www.acmicpc.net/problem/2864

# 풀이:

두 정수 A 와 B 의 숫자 중

5 와 6 을 전부 5 로 바꾼 값들을 더한 값이 최솟값,

6 으로 바꾼 값들을 더한 값이 최댓값이 된다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;
int main() {
	string a, b, c, d, e, f;
	cin >> a >> b;
	for (char i : a)
		if (i == 54 || i == 53)	c += '6', d += '5';
		else c += i, d += i;
	for (char i : b)
		if (i == 54 || i == 53)	e += '6', f += '5';
		else e += i, f += i;
	printf("%d %d\n", stoi(d) + stoi(f), stoi(c) + stoi(e));
}
```

