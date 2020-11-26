# [백준]11399 ATM

[https://www.acmicpc.net/problem/11399](http://www.acmicpc.net/problem/11399)

# **풀이:**
1. 돈을 인출하는데 필요한 시간을 입력받는다.
2. 입력받은 시간을 정렬한다.
3. 정렬한 값을 n-i를 곱해서 더해준다.

# **코드:**
사용언어 : c++
```C++
#include <iostream>
#include <algorithm>
using namespace std;
int main() {
	int n,r=0,a[1001];
	cin >> n;
	for (int i = 0; i < n; i++)
		cin >> a[i];
	sort(&a[0], &a[n]);
	for (int i = 0; i < n; i++)
		r += a[i] * (n - i);
	cout << r << endl;
}
```
