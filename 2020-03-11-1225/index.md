# [백준]1225 이상한 곱셈

https://www.acmicpc.net/problem/1225

# 풀이:

123 * 45



-> 1\*4 + 1\*5 + 2\*4 + 2\*5 + 3\*4 + 3\*4

-> 1(4 + 5) + 2(4 + 5) + 3(4 + 5)

-> (1 + 2 + 3)(4 + 5)



즉, (왼쪽 숫자의 각 자릿수의 합) * (오른쪽 숫자의 각 자릿수의 합) 이다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
long long q = 0, w = 0, i;
int main() {
	string a, b;
	cin >> a >> b;
	for (i = 0; i < a.size(); i++) q += a[i] - '0';
	for (i = 0; i < b.size(); i++) w += b[i] - '0';
	cout << q * w << endl;
}
```

