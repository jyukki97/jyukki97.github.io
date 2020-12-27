# [백준]17263 Sort 마스터 배지훈


https://www.acmicpc.net/problem/17263

# 풀이:

받아온 수 중 가장 큰 수를 출력한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
using namespace std;

int main() {
	int n, a, c = 0;
	cin >> n;
	while (n--) {
		cin >> a;
		if (c < a) c = a;
	}
	cout << c << endl;
}
```
