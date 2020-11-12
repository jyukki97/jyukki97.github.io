# [백준]1057 토너먼트

https://www.acmicpc.net/problem/1057

# 풀이:

​		  1					  2	

​	1		  2		  3		 4

1	2	3	4	5	6	7	8



현재 번호가 i 라고 할 때,

위로 갈 수록 배정받는 번호는 (i + 1) / 2 가 된다.

즉, 김지민과 임한수의 번호가 x, y 라고 할 때,

( x + 1 )  / 2 == ( y + 1 ) / 2 

가 되는 순간이 둘이 대결하는 순간이다.

토너먼트가 끝날 때까지 둘이 대결하지 않는 경우는 없으므로 -1 출력은 하지않는다.





# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, a, b, c = 0;
int main() {
	cin >> n >> a >> b;
	a--;
	b--;
	while (a != b) {
		a /= 2;
		b /= 2;
		c++;
	}
	cout << c << endl;
}
```

