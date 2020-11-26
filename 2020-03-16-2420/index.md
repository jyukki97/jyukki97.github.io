# [백준]2420 사파리월드

https://www.acmicpc.net/problem/2420

# 풀이:

두 유명도의 차이를 절댓값으로 출력한다.



###### 두 도메인의 크기가 매우 크므로 long long 으로 받자.

###### long long 형으로 받았으므로 abs 가 아닌 llabs를 쓰자

# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
long long a, b;
int main() {
	cin >> a >> b;
	cout << llabs(a - b) << endl;
}
```

