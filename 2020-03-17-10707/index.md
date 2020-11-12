# [백준]10707 수도요금

https://www.acmicpc.net/problem/10707

# 풀이:

X사의 1리터당 요금 * 한 달간의 수도의 양

Y사의 기본요금 + (Y사의 1리터당 추가요금 * (한 달간의 수도의 양 - 기본요금이 되는 사용량의 상한))

둘 중 더 싼 금액을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a, b, c, d ,p;
int main() {
	cin >> a >> b >> c >> d >> p;
	a *= p, b += p < c ? 0 : (p - c) * d;
	printf("%d\n", a < b ? a : b);
}
```

