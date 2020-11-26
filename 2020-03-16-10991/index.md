# [백준]10991 별 찍기 - 16

https://www.acmicpc.net/problem/10991

# 풀이:

N개의 줄에 N개의 글자를 출력한다.

첫 줄에는 N-1개의 " "와 1개의 "* "을

두 번째 줄에는 N-2개의 " "와 2개의 "* "을

.

.

.

i번째 줄에는 N-i개의 " "와 i개의 "* "을



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
		for (; t <= N; t++) cout << "* ";
		cout << endl;
	}
}
```

