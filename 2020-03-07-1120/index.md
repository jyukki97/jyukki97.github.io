# [백준]1120 문자열

https://www.acmicpc.net/problem/1120

# 풀이:

a 와 b의 (0번째 ~ a의 길이) 의 차이의 개수

a 와 b의 (1번째 ~ a의 길이) 의 차이의 개수

.

.

.

a 와 b의 ()(b의 길이 - a의 길이)번째 ~ a의 길이) 의 차이의 개수



중 가장 작은것을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	int c = 51;
	string a, b;
	cin >> a >> b;
	for (int i = 0; i <= b.size() - a.size(); i++) {
		int d = 0;
		for (int t = 0; t < a.size(); t++)
			if (a[t] != b[t + i]) d++;
		c = c > d ? d : c;
	}
	cout << c << endl;
}
```

