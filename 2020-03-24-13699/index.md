# [백준]13699 점화식

https://www.acmicpc.net/problem/13699

# 풀이:

- t(0) = 1
- t(1) = t(0)*t(0) = 1
- t(2) = t(0)\*t(1)+t(1)*t(0) = 2
- t(3) = t(0)\*t(2)+t(1)\*t(1)+t(2)*t(0) = 5

주어진 점화식 그대로 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
long long n, t, i = 1, a[36] = { 1 };
int main() {
	cin >> n;
	for (; i <= n; i++)	for (t = 0; t < i; t++)	a[i] += a[i - t - 1] * a[t];
	cout << a[n] << endl;
}
```

