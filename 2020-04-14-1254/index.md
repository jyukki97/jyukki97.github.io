# [백준]1254 팰린드롬 만들기

https://www.acmicpc.net/problem/1254

# 풀이:

기준점 i를 잡는다. (초기 i값은 문자열 S의 중간 지점)

기준점 i와 i - 1을 기준으로 짝수 팰린드롬을 만들 수 있는지 확인한다.

만들 수 없다면,

기준점 i를 기준으로 홀수 팰린드롬을 만들 수 있는지 확인한다.

만들 수 없다면,

기준점 i를 +1 해준다.



짝수 팰린드롬을 만들 수 있다면, 2 * ( i - 1 ) 을 출력한다.

홀수 팰린드롬을 만들 수 있다면, 2 *  i - 1 을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int i, c, f, k, t;  string s;
int main() {
	cin >> s;
	c = s.size();
	for (i = c / 2; !f && i < c; i++) {
		for (t = 1; t + i - 1 < c && i > (c - 1) / 2; t++) {
			f = 1, k = 1;
			if (s[i + t - 1] != s[i - t]) {
				f = 0, k = 0;
				break;
			}
		}
		for (t = 1; !k && t + i < c; t++) {
			f = 1;
			if (s[i + t] != s[i - t]) {
				f = 0;
				break;
			}
		}
	}
	printf("%d", k ? 2 * (i - 1) : 2 * i - 1);
}
```

