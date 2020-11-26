# [백준]9316 Hello Judge

https://www.acmicpc.net/problem/9316

# 풀이:

한 줄에 하나의 Hello World, Judge i! 를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	int a;
	cin >> a;
	for (int i = 1; i <= a; i++)printf("Hello World, Judge %d!\n", i);
}
```

