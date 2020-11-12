# [백준]17173 배수들의 합

https://www.acmicpc.net/problem/17173

# 풀이:

2 ~ n 까지 수들 중 ki 중 하나의 배수인 수를 모두 찾아 더한 후 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int n, m, i, t, s = 0, a[1001];
int main() {
	cin >> n >> m;
	for (i = 0; i < m; i++) cin >> a[i];
	for (i = 2; i <= n; i++)
		for (t = 0; t < m; t++)
			if (!(i % a[t])) {
				s += i;
				break;
			}
	cout << s << endl;
}
```

