# [백준]4999 아!

https://www.acmicpc.net/problem/4999

# 풀이:

의사가 듣기 원하는 소리의 길이가 재환이가 가장 길게 낼 수 있는 소리보다 크다면,

"no"를 아니라면 "go" 를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	string a, b;
	cin >> a >> b;
	printf("%s\n", a.size() < b.size() ? "no" : "go");
}
```

