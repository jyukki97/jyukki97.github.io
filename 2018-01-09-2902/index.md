# 2902 KMP는 왜 KMP일까?

[https://www.acmicpc.net/problem/2902](http://www.acmicpc.net/problem/2902)

#### **풀이:**
1. 대문자를 출력

#### **코드:**

```
#include <iostream>
#include <string>
using namespace std;
string a;
int main(void) {
	cin >> a;
	for (int i = 0; i < a.length(); i++) {
		if (a[i] > 64 && a[i] < 91)
			cout << a[i];
	}
	cout << endl;
}
```
