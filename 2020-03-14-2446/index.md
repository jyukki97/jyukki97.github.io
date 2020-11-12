# [백준]2446 별 찍기 - 9

https://www.acmicpc.net/problem/2446

# 풀이:

[[백준\]2442 별찍기 - 5](https://jyukki97.github.io/blog/2020-03-12-2442/) 에 나온 삼각형을 방향을 반대로 2번 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n;
int main() {
	cin >> n;
	for (int i = 0; i < n - 1; i++) {
		for (int t = 0; t < i; t++) cout << " ";
		for (int t = 1; t < (n -i) * 2; t++) cout << "*";
		cout << endl;
	}
	for (int i = 0; i < n; i++) {
		for (int t = 1; t < n - i; t++) cout << " ";
		for (int t = 0; t < i * 2 + 1; t++) cout << "*";
		cout << endl;
	}
}
```

