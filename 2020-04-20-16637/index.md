# [백준]16637 괄호 추가하기

https://www.acmicpc.net/problem/16637

# 풀이:

순서대로 사칙연산을 진행한다.

이 때, 현재 숫자만 계산하는 것, 현재 숫자 (연산자) 다음 숫자 를 계산하는 것 두 가지로 나누어 생각한다.



현재 숫자만 계산하는 것은, 이전에 계산했던 숫자 (연산자) 현재 숫자

두번째 경우는, 이전에 계산했던 숫자 (연산자) ( 현재 숫자 (연산자) 다음 숫자 )



이렇게 두 가지 경우로 모든 구간을 연산하여 완전탐색을 돌린다.



정답의 범위가 -2^31 ~ 2^31 이므로 최댓값의 초기값을 0으로 하지않도록 주의하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
long long n, m = -2e31;	string s;
void O(int x, int y, long long z) {
	long long q;
	if (x + y >= n)	return;
	if (y) {
		if (s[x + 1] == '+') q = s[x] + s[x + 2] - 96;
		if (s[x + 1] == '-') q = s[x] - s[x + 2];
		if (s[x + 1] == '*') q = (s[x] - '0') * (s[x + 2] - '0');
	}
	else q = s[x] - '0';
	if (!x || s[x - 1] == '+')	z += q;
	else if (s[x - 1] == '-')	z -= q;
	else if (s[x - 1] == '*')	z *= q;
	if (x + 2 * y > n - 2) {
		m = m < z ? z : m;
		return;
	}
	O(x + 2 * (y + 1), 0, z);
	O(x + 2 * (y + 1), 1, z);
}
int main() {
	cin >> n >> s;
	O(0, 0, 0);
	O(0, 1, 0);
	cout << m << endl;
}
```

