# [백준]13458 시험 감독

https://www.acmicpc.net/problem/13458

# 풀이:

각 시험장에 총감독관 1명씩이 꼭 들어간다.

즉 각 시험장에 있는 응시자의 수에서 총감독관이 감시할 수 있는 응시자의 수 B를 빼준다.

빼준 값에서 부감독관이 감시할 수 있는 응시자의 수 C를 나눈 값을 올림해 준다면,

부감독관의 수가 나온다.

감독관들의 수를 모두 더한값을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <math.h>
using namespace std;
long long n, i, b, c, a[1000002], s = 0;
int main() {
	cin >> n;
	for (i = 0; i < n; i++)	cin >> a[i];
	cin >> b >> c;
	for (i = 0; i < n; i++) {
		a[i] -= b;
		if (a[i] > 0)	s += ceil((double)a[i] / c);
		s++;
	}
	cout << s << endl;
}
```

