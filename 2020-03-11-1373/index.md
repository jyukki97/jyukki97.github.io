# [백준]1373 2진수 8진수

https://www.acmicpc.net/problem/1373

# 풀이:

2진수를 8진수로 변환하여 출력.



변환하는 방법은



11001100(2) 일때,

뒤에서 부터 3자리로 끊어서 생각한다.



 011 001 100

-> 3	1	 4 



주어진 수의 '길이' 가 1,000,000 까지 갈 수 있으므로 주의하자.

(수가 1,000,000 이 아니다. 수의 길이 이므로 엄청나게 큰 수가 들어온다.)



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;
int b, c, i, t;
int main() {
	string s, a;
	cin >> s;
	for (i = s.size() - 1; i >= 0; i -= 3) {
		c = 1, b = 0;
		for (t = 0; t < 3; t++) {
			if (i >= t && s[i - t] == '1') b += c;
			c *= 2;
		}
		a += to_string(b);
	}
	for (i = a.size() - 1; i >= 0; i--) cout << a[i];
	cout << endl;
}
```

