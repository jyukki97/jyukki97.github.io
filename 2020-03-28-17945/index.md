# [백준]17945 통학의 신

https://www.acmicpc.net/problem/17945

# 풀이:

x2 + 2Ax + B = 0 의 두 계수 A, B가 주어진다

두 근을 구해 출력하는 문제.

근의 공식을 이용하자!



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
#include <math.h>
using namespace std;
int a, b, c, d;;
int main() {
	cin >> a >> b;
	c = -a - sqrt(a * a - b);
	d = -a + sqrt(a * a - b);
	printf(c == d ? "%d" : "%d %d",c, d);
}
```

