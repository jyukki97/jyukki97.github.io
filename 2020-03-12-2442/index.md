# [백준]2442 별 찍기 - 5

https://www.acmicpc.net/problem/2442

# 풀이:

1 번째 줄부터 차례대로



1개

3개

5개

.

.

.

i * 2 - 1 개

의 별을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t;
int main() {
	cin >> n;
	for (i = 1; i <= n; i++) {
		for (t = 0; t < n - i; t++)	cout << " ";
		for (t = 0; t < 2 * i - 1; t++) cout << "*";
		cout << endl;
	}
}
```

