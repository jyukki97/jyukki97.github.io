# [백준]1159 농구 경기

https://www.acmicpc.net/problem/1159

# 풀이:

각 선수의 성의 첫글자를 확인한다.

a ~ z 까지의 배열 에서 첫글자에 해당하는 배열을 +1 해준다.



a~ z 까지 확인한다.

5명 이상인 글자는 출력한다.



만약, 출력한 글자가 없다면, "PREDAJA" 를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int N, a[26], b = 0, i = 26;
int main() {
	cin >> N;
	while(N--) {
		string s;
		cin >> s;
		a[122 - s[0]]++;
	}
	while(i--)
		if (a[i] > 4) {
			b = 1;
			cout << char(122 - i);
		}
	if (!b)	cout << "PREDAJA";
	cout << endl;
	
}
```

