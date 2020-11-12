# [백준]11382 꼬마 정민

https://www.acmicpc.net/problem/11382

# 풀이:

A, B, C 를 각각 문자열로 변환한다.

변환된 문자열을 한자리씩 더한다.

만약 각 자릿수의 숫자가 10이 넘어간다면 다음 자릿수에 올림을 해준다.



더해진 문자열을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int main() {
	string a, b, c, d;
	cin >> a >> b >> c;
	int m = max(a.size(), max(b.size(), c.size())), s = 0;
	for (int i = 1; i <= m; i++) {
		if (a.size() >= i)	s += a[a.size() - i] - '0';
		if (b.size() >= i)	s += b[b.size() - i] - '0';
		if (c.size() >= i)	s += c[c.size() - i] - '0';
		d += (s % 10) + '0';
		s /= 10;
		if (i == m && s)	d += s + '0';
	}
	reverse(d.begin(), d.end());
	cout << d << endl;
}
```

