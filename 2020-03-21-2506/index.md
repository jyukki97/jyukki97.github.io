# [백준]2506 점수 계산

https://www.acmicpc.net/problem/2506

# 풀이:

연속으로 맞춘다면 추가 점수가 있게 하여 총점을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, s, c = 0, a;
int main() {
	cin >> n;
	while (n--) {
		cin >> a;
		if (a) s += a + c, c++;
		else c = 0;
	}
	cout << s << endl;
}
```

