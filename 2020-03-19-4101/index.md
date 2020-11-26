# [백준]4101 크냐?

https://www.acmicpc.net/problem/4101

# 풀이:

첫 번째 수가 두 번째 수보다 크면 Yes를, 아니면 No를 한 줄에 하나씩 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int a, b;
int main() {
	while (1) {
		cin >> a >> b;
		if (!a && !b)break;
		printf("%s\n", a > b ? "Yes" : "No");
	}
}
```

