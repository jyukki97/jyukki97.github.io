# [백준]13909 창문 닫기

https://www.acmicpc.net/problem/13909

# 풀이:

n 까지의 창문들 중 열려있는 창문들은 제곱수 이다.

즉 n까지의 창문들 중 제곱수의 갯수를 찾아 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i;
int main() {
	cin >> n;
	while (i * i <= n) i++;
	cout << i - 1 << endl;
}
```

