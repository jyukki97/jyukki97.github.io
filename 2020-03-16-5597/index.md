# [백준]5597 과제 안 내신 분..?

https://www.acmicpc.net/problem/5597

# 풀이:

과제를 낸 28 명을 기록한다.

30 명 중 기록이 안돼어있는 학생 2명을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a[31], i = 28, b;
int main() {
	while (i--) {
		cin >> b;
		a[b] = 1;
	}
	for (i = 1; i <= 30; i++)	if (!a[i])	cout << i << endl;
}
```

