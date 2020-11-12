# [백준]3613 Java vs C++


https://www.acmicpc.net/problem/3613

# **풀이:**
1. java 변수면 c++로 c++ 이면 java로 변경
2. 예외처리

# **코드:**

```c++
#include <iostream>
#include <string.h>
using namespace std;

int main(void) {
	char a[201];
	char b[201] = {'\n'};
	bool java = false;
	bool cplus = false;
	bool ero = true;
	cin >> a;
	int t = 0;
	for (int i = 0; i < strlen(a); i++) {
		if (65 <= (int)a[i] && (int)a[i] <= 90) {
			if (i == 0 || cplus == true) {
				ero = false;
				break;
			}
			b[t] = '_';
			t++;
			b[t] = a[i] + 32;
			java = true;
		}
		else if (a[i] == '_') {
			if (i == 0 || i == strlen(a)-1 || a[i + 1] == '_' || java == true || (65 <= (int)a[i + 1] && (int)a[i + 1] <= 90)) {
				ero = false;
				break;
			}
			b[t] = a[i + 1] - 32;
			i++;
			cplus = true;
		}
		else 
			b[t] = a[i];
			t++;
	}
	if (ero == false)
		cout << "Error!" << endl;
	else
		cout << b << endl;

	return 0;
}
```


