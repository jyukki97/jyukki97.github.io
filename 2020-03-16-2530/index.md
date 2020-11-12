# [백준]2530 인공지능 시계

https://www.acmicpc.net/problem/2530

# 풀이:

요리에 필요한 시간 D를 초에 더한다.

초 C를 60으로 나눈 몫을 분에 더한다.	초는 나눈 나머지가 된다.

분 B를 60으로 나눈 몫을 시에 더하다.	분은 나눈 나머지가 된다.

시를 24로 나눈 나머지로 바꾼다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a, b, c, d;
int main() {
	cin >> a >> b >> c >> d;
	c += d, b += c / 60, c %= 60, a += b / 60, b %= 60, a %= 24;
	printf("%d %d %d", a, b, c);
}
```

