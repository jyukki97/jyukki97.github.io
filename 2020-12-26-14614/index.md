# [백준]14614 Calculate!


https://www.acmicpc.net/problem/14614

# 풀이:

C가 짝수라면 A를



C가 홀수라면 A 와 B를 XOR한 값을 출력한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
using namespace std;

int main() {
	int a, b;
	string c;
	cin >> a >> b >> c;
	if ((int)(c[c.size() - 1] - '0') % 2) a ^= b;
	cout << a << endl;
}
```
