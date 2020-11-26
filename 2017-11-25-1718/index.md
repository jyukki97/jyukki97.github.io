# [백준]1718 암호


https://www.acmicpc.net/problem/1718

# **풀이:**
1. 평문에서 암호문을 뺀다.
2. 만약 뺀 값이 0 이하일경우 z로 돌아간다.

# **코드:**

```C++
#include <iostream>
#include <string>
using namespace std;

int main(void) {
	string a;
	getline(cin, a);
	string key;
	cin >> key;
	char cy[30001] = { NULL };
	for (int i = 0; i < a.length(); i++) {
		if (a[i] == ' ')
			cy[i] = ' ';
		else if ((int)a[i] - (int)key[i%key.length()] <= 0)
			cy[i] = (char)((int)a[i] - (int)key[i%key.length()] + 122);
		else
			cy[i] = (char)((int)a[i] - (int)key[i%key.length()] + 96);
	}
	cout << cy << endl;
	return 0;
}
```


