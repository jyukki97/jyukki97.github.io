# [백준]1024 수열의 합

https://www.acmicpc.net/problem/1024

# 풀이:

길이가 적어도 L인 수열은 다음과 같이 나타낼 수 있다.

```c++
n	n + 1	n + 2	...		n + L - 2	n + L - 1
```

즉, 길이가 L인 수열들의 합은

L * n + Σ k (k = 1 ~ L - 1) = N



( N - Σ k (k = 1 ~ L - 1) ) % L == 0

인 L을 찾는다면, 답을 구할 수 있다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int N, L, s, a;
int main() {
	cin >> N >> L;
	while (L <= 100) {
		s = L, a = 0;
		while (s--)	a += s;
		if (N < a)	L = 101;
		else if (!((N - a) % L))	break;
		L++;
	}
	if (L <= 100) {
		a = (N - a) / L;
		while(L--)	cout << a++ << " ";
	}
	else	cout << -1;
	cout << endl;
}
```

