# [백준]10422 괄호

https://www.acmicpc.net/problem/10422

# 풀이:

C1=C0C0

C2=C0C1+C1C0

C3=C0C2+C1C1+C2C0

C4=C0C3+C1C2+C2C1+C3C0

.

.

.

Cn = ΣCiC(n - i - 1)



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
long long T, n, t, i = 2, a[3000] = { 1,1 };
int main() {
	cin >> T;
	while (T--) {
		cin >> n;
		if (n % 2)	cout << "0" << endl;
		else {
			for (; i <= n / 2; i++)	for (t = 0; t < i; t++)	
                a[i] = (a[i] + a[i - t - 1] * a[t]) % 1000000007;
			cout << a[n / 2] << endl;
		}
	}
}
```

