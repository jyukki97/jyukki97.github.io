# [백준]11109 괴짜 교수

https://www.acmicpc.net/problem/11109

# 풀이:

병렬화를 하는게 좋으면 "parallelize" 를 출력하고, 병렬화를 하는게 좋지 않으면 "do not parallelize" 를 출력한다. 만약 직렬화와 병렬화를 통한 시간이 같으면 "does not matter" 를 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int T, d, n, s, p;
int main() {
	cin >> T;
	while (T--) {
		cin >> d >> n >> s >> p;
		printf("%s\n",d + n * p > n* s ? "do not parallelize" : d + n * p < n * s ? "parallelize" : "does not matter");
	}
}
```

