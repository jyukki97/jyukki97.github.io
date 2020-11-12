# [백준]1334 다음 팰린드롬 수

https://www.acmicpc.net/problem/1334

# 풀이:

문자열 S를 받아온다.

S의 길이를 N이라고 하자.

S의 오른쪽 절반의 값을 왼쪽 절반의 값으로 덮어쓰자.

그렇게 만들어진 문자열을 A라고 하자.

A는 이미 펠린드롬 수 인데, 이 수가 S보다 크다면 A를 그대로 출력한다.

만약 S보다 작다면, 

가운데 수를 1씩 증가시킨다.

가운데 수가 9가 됐다면, 0으로 바꾸고 오른쪽, 왼쪽 수를 1씩 증가시킨다.

더 커질 때까지 반복한 후 A를 출력한다.



만약 S가 9로만 이루어진 수라면, 맨 앞수를 1로 바꾸고 그 것을 제외한 모든수를 0으로 바꾼 후 1을 추가한 후 출력한다.

EX) 999 -> 1001





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, f;  string s, a;
int main() {
	cin >> s;
	a = s;
	n = a.size();
	string p(n, '9');
	if (a == p) {
		for (i = 0; i < n; i++) a[i] = '0';
		a[0] = '1', a += '0', n++;
		s.insert(s.begin(), '0');
	}
	for (i = n - 1; i >= n / 2; i--)	a[i] = a[n - i - 1];
	for (i = 0; i < n; i++)	
		if (a[i]!=s[i]) {
			f = a[i] > s[i];
			break;
		}
	for (i = n / 2; !f && i < n; i++) {
		if (a[i] > s[i] || a[n - i - 1] > s[n - i - 1])	break;
		if (a[i] == '9') {
			if (!(n % 2) || i != n / 2) a[n - i - 1] = '0';
			a[i] = '0';
			continue;
		}
		if (a[i] <= s[i]) {
			if (i != n - i - 1)	a[n - i - 1]++;
			a[i]++, i--;
		}
	}
	cout << a << endl;
}
```

