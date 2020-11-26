# [백준]11047 동전 0

[https://www.acmicpc.net/problem/11047](http://www.acmicpc.net/problem/11047)

# **풀이:**
1. 동전에 가격이 높은 것 부터 내가 필요한 가격에서 빼준다.
2. 빼준 횟수만큼 카운트를 높여준다.
3. 카운트를 출력한다.
4. ( i ≥ 2인 경우에 Ai는 Ai-1의 배수) 조건으로 인해 그냥 높은 것 부터 빼줘도 문제가 생기지않는다.

# **코드:**
사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	int n, k, s[12], c = 0;
	cin >> n >> k;
	while (n--)
		cin >> s[n];
	while (k) {
		c += k / s[++n]; 
		k %= s[n];
	}
	cout << c << endl;
	return 0;
}

```
