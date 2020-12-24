# [백준]12779 상품 is 뭔들


https://www.acmicpc.net/problem/12779

# 풀이:

약수의 갯수가 홀수라는 것은 "제곱수" 라는 것을 의미한다.

그러므로 제곱수의 갯수 / 전체 갯수를 한다면 답을 구할 수 있다.



주의

1. 확률이 0일 경우 0을 출력해야한다.
2. 2^60 까지의 숫자이므로 int형에 들어갈 수 없다.
3. 기약분수로 출력해야하므로 최대 공약수로 나누어주는 작업을 해주자.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <math.h>
using namespace std;

long long gcd(long long a, long long b)
{
	return b ? gcd(b, a % b) : a;

}
int main() {
	long long a, b, i, g, c = 0;
	cin >> a >> b;
	for (i = sqrt(a); i * i <= b; i++) {
		c += i * i > a ? 1 : 0;
	}
	if (c == 0) {
		cout << 0 << endl;
	}
	else {
		g = gcd(b - a, c);
		cout << c / g << "/" << (b - a) / g << endl;
	}
}
```
