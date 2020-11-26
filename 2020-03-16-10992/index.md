# [백준]10992 별 찍기 - 17

https://www.acmicpc.net/problem/10992

# 풀이:

첫줄에 1개, 마지막줄에 2 * N - 1개

i번째 줄에는 N - i 칸 띄고, "*" 한개, 2 * i - 1 칸 띄고, "*" 한개

출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int N, i, t;
int main() {
	cin >> N;
	for (i = 0; i < N; i++) {
		for (t = 1; t < N - i; t++)	cout << " ";
		cout << "*";
		for (t = 0; t < 2 * i - 1; t++) printf("%s", i == N - 1 ? "*" : " ");
		printf("%s\n",!i?"":"*");
	}
	cout << endl;
}
```

