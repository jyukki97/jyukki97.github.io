# [백준]11655 ROT13

https://www.acmicpc.net/problem/11655

# 풀이:

ROT13으로 암호화한 내용을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <string>
using namespace std;
int main() {
	string s;
	getline(cin, s);
	for (char c : s)	
       printf("%c", c < 65 ? c : (c < 97 && c > 77) || c > 109 ? c - 13 : c + 13);
	cout << endl;
}
```

