# [백준]2566 최댓값

https://www.acmicpc.net/problem/2566

# 풀이:

9 * 9 칸에 있는 숫자들 중 최댓값과 그 위치를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int i, a, x, c = 0;
int main() {
	for (i = 0; i < 81; i++){
			cin >> a;
			if (a > c)	c = a, x = i;
		}
	printf("%d %d %d", c, x / 9 + 1, x % 9 + 1);
}
```

