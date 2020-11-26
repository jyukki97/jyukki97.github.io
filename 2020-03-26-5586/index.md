# [백준]5586 JOI와 IOI

https://www.acmicpc.net/problem/5586

# 풀이:

문자열에 포함되어 있는 JOI의 개수, 둘째 줄에 IOI의 개수를 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int a, b, i; string s;
int main() {
	cin >> s;
	for (i = 0; i < s.size() - 2; i++)
		if (s.substr(i, 3) == "JOI")	a++;
		else if (s.substr(i, 3) == "IOI")	b++;
	printf("%d\n%d", a, b);
}

```

