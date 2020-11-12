# [백준]2523 별 찍기 - 13

https://www.acmicpc.net/problem/2523

# 풀이:

증가하는 순서로 별을찍다가 n+1 번쨰 줄부터 감소하는 순서로 별을 찍는다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t;
int main() {
	cin >> n;
	for (i = 0; i < n; i++) {	
		for (t = 0; t <= i; t++)	cout << "*";
		cout << endl;
	}
	while (n--) {
		for (t = 0; t < n; t++)	cout << "*";
		cout << endl;
	}
}
```

