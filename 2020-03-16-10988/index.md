# [백준]10988 팰린드롬인지 확인하기

https://www.acmicpc.net/problem/10988

# 풀이:

###### 팰린드롬 : 기러기, 토마토 등 뒤집어도 같은단어



주어진 단어가 팰린드롬이라면 1, 아니라면 0을 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int main() {
	string a; bool b = true;
	cin >> a;
	for (int i = 0; i < a.size() / 2; i++)	
        if (a[i] != a[a.size() - i - 1]) 
            b = false;
	if (b)	cout << "1" << endl;
	else cout << "0" << endl;
}
```

