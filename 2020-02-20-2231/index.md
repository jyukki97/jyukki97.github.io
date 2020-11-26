# [백준]2231 분해합

https://www.acmicpc.net/problem/2231

# 풀이:

n - (n의 자릿수 * 9) ~ n 까지의 수 중 n의 생성자를 찾아 출력한다.

없다면 0을 출력



n의 자릿수 * 9를 뺀 수부터 시작하는 이유는 생성자가 n + (n의 각 자릿수의 합) 이므로 

각 자릿수의 최댓값인 9를 자릿수 만큼 곱한 후 n에서 빼준 값이 생성자의 최소 조건이 된다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;

int c(int a) {
	int n = a;
	while (a) {
		n += a % 10;
		a /= 10;
	}
	return n;
}

int main() { 
	string m;
	bool b = true;
	cin >> m;
	int n = stoi(m), a = n - 9 * m.size();
	if (a < 0)	a = 1;
	for (int i = a; i <= n; i++)
			if (c(i) == n) {
				b = false;
				cout << i << endl;
				break;
			}
	if (b) cout << 0 << endl;
	return 0;
}
```

