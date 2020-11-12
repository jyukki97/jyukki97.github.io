# [백준]10824 네 수

https://www.acmicpc.net/problem/10824

# 풀이:

A, B, C, D 를 각각 string으로 받아 붙힌 후

숫자로 변환하여 더해 출력한다.



###### stoi 는 int형식으로 각각 1,000,000 까지 가능 한 두 수를 붙힌다면 넘어가므로 stoll을 사용하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;
string a,b,c,d;
int main() {
	cin >> a >> b >> c >> d;
	cout << stoll(a + b) + stoll(c + d) << endl;
}
```

