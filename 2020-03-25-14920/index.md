# [백준]14920 3n+1 수열

https://www.acmicpc.net/problem/14920

# 풀이:

```c++
     C(n+1) = C(n)/2     (C(n)이 짝수일 때)
            = 3*C(n)+1   (C(n)이 홀수일 때)
```

주어진 점화식대로 진행하다가 C(n)이 1이되었을 때, n을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a, i = 1;
int main() {
	for (cin >> a;a!=1; i++)
		a = a % 2 ? 3 * a + 1 : a / 2;
	cout << i << endl;
}
```

