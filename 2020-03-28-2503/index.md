# [백준]2503 숫자 야구

https://www.acmicpc.net/problem/2503

# 풀이:

123 ~ 987 까지의 중복이 없는 숫자를 모두 탐색한다.

각 숫자를 n개의 질문과 대조하여 틀린점이 없다면 답을 +1 해준다.



모든 숫자를 탐색했다면 답을 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int n, i, a, s[100], b[100]; string c[100], m;
void B(int x) {
	if (x == 3) {
		int r = 1;
		for (int t = 0; t < n; t++) {
			int q = 0, w = 0;
			for (int y = 0; y < 3; y++)
				for (int u = 0; u < 3; u++)
					if (c[t][y] == m[u])
						if (y == u)	q++;
						else w++;
			if (s[t] != q || b[t] != w)	r = 0;
		}
		if (r)	a++;
	}
	for (int t = 1; t < 10; t++) {
		if (!x || (x == 1 && m[0] - '0' != t)
			|| (x == 2 && m[0] - '0' != t && m[1] - '0' != t))	
            m[x] = '0' + t, B(x + 1);
	}
}
int main() {
	cin >> n;
	for (i = 0; i < n; i++)		cin >> c[i] >> s[i] >> b[i];
	m.resize(4);
	B(0);
	cout << a << endl;
}
```

