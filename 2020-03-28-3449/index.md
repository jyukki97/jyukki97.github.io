# [백준]3449 해밍 거리

https://www.acmicpc.net/problem/3449

# 풀이:

각 테스트 케이스에 대해서, 해밍 거리를 계산한 뒤, "Hamming distance is X."라고 출력한다.



해밍 거리란?

> 각 문자열의 문자들 중 서로 다른 문자열의 갯수!



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int T, i, s; string a, b;
int main() {
	cin >> T;
	while (T--) {
		cin >> a >> b;
		for (s = 0,i = 0; i < a.size(); i++)	s += a[i] != b[i] ? 1 : 0;
		printf("Hamming distance is %d.\n", s);
	}
}
```

