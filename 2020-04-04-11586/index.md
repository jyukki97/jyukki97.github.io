# [백준]11586 지영 공주님의 마법 거울

https://www.acmicpc.net/problem/11586

# 풀이:

문자열을

k가 1일 경우 그대로

k가 2일 경우 좌우 반전

k가 3일 경우 상하 반전



으로 출력한다. 



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t, k; string s[101];
int main() {
	cin >> n;
	for (; i < n; i++) cin >> s[i];
	cin >> k;
	if (k == 1)
		for (i = 0; i < n; i++)
			cout << s[i] << endl;
	else if (k == 2)
		for (i = 0; i < n; i++,printf("\n"))
			for (t = n - 1; t >= 0; t--)
				cout << s[i][t];
	else
		for (i = n - 1; i >= 0; i--)
			cout << s[i] << endl;
}
```

