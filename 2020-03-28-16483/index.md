# [백준]16483 접시 안의 원

https://www.acmicpc.net/problem/16483

# 풀이:

a^2 = (T/2)^2 + b^2

a^2 - b^2 = (T/2)^2



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int T;
int main() {
	cin >> T;
	printf("%d", T*T/4);
}
```

