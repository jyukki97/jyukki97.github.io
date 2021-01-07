# [백준]12787 지금 밥이 문제냐


https://www.acmicpc.net/problem/12787

# 풀이:

IPv8 주소가 주어진다면, 정수로



정수가 주어진다면, IPv8 주소로 변환하여 출력한다.



정수의 범위가 64비트이므로 unsigned long long 형을 사용하도록 하자!!



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <string>
#include <string.h>
#define ul unsigned long long
using namespace std;
ul c;
int main() {
	int i, t, y, n, m, d;
	cin >> n;
	while (n--) {
        string s;
		cin >> m;
		if (m == 1) {
			char *r = new char[40], *e;
			cin >> r;
			i = 8, c = 0;
			e = strtok(r, ".");
			do {
				i--, y = atoi(e);
				for (t = 7; t >= 0; t--)
					if (y & (1 << t)) c |= (ul)1 << ((i * 8) + t);
			} while (e = strtok(NULL, "."));
			cout << c << endl;
		}
		else {
			cin >> c;
			for (i = 7; i >= 0; i--, s += to_string(d) + '.')
				for (d = 0, t = 7; t >= 0; t--)
					if (c & (ul)1 << ((i * 8) + t)) d |= 1 << t;
			s.erase(s.end()-1);
			cout << s << endl;
		}
	}
}
```
