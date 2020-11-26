# [백준]5598 카이사르 암호

https://www.acmicpc.net/problem/5598

# 풀이:

입력받은 카이사르 단어를 원래 단어로 고친 걸 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	string s;
	cin >> s;
	for (char c : s) printf("%c", c < 68 ? c + 23 : c - 3);
	cout << endl;
}
```

