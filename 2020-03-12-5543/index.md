# [백준]5543 상근날드

https://www.acmicpc.net/problem/5543

# 풀이:

햅버거 중 가장 싼 것  + 음료 중 가장 싼 것 - 50원



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a,b,c,d,e;
int main() {
	cin >> a >> b >> c >> d >> e;
	a = a < b ? a : b;
	a = a < c ? a : c;
	d = d < e ? d : e;
	cout << a + d - 50 << endl;
}
```

