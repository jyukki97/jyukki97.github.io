# [백준]2460 지능형 기차 2

https://www.acmicpc.net/problem/2460

# 풀이:

기차에 사람이 가장 많을 때의 사람 수를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a, b, i, s = 0, t = 0;
int main() {
	for (i = 0; i < 10; i++) {
		cin >> a >> b;
		s += b - a, t = t < s ? s : t;
	}
	cout << t << endl;	
}
```

