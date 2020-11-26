# [백준]2953 나는 요리사다

https://www.acmicpc.net/problem/2953

# 풀이:

첫째 줄부터 다섯번쨰 줄까지의 사람 중 점수의 합이 가장 높은 사람과 그 점수를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int i, a, b, c, d, s, t = 0;
int main() {
	for (i = 1; i < 6; i++) {
		cin >> a >> b >> c >> d;
		a += b + c + d;
		if (a > t)	t = a, s = i;
	}
	printf("%d %d", s, t);
}
```

