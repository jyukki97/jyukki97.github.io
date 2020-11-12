# [백준]2748 피보나치 수 2


[https://www.acmicpc.net/problem/2748](http://www.acmicpc.net/problem/2748)

# **풀이:**
1. a[i % 3]
	: n번째 피보나치 수
2. a[i % 3] = a[(i - 1) % 3] + a[(i - 2) % 3];
   

# **코드:**

```c++
#include <iostream>
using namespace std;
long long a[3] = { 0,1 }, n;
int main() {
	cin >> n;
	for (int i = 2; i <= n; i++)
		a[i % 3] = a[(i - 1) % 3] + a[(i - 2) % 3];
	cout << a[n % 3] << endl;
}
```
