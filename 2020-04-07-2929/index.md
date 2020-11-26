# [백준]2929 머신 코드

https://www.acmicpc.net/problem/2929

# 풀이:

만약 머신 코드의 명령(대문자) 이 들어왔는데, 그 위치가 4의 배수가 아니라면, 

4의 배수가 될 때까지 NOP의 갯수를 증가시킨다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int i, c; string s;
int main() {
	cin >> s;
	for (i = 0; i < s.size(); i++)
        while (isupper(s[i]) && (i + c) % 4 != 0) c++;
	cout << c << endl;
}
```

