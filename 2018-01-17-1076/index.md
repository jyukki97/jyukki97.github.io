# 1076 저항

[https://www.acmicpc.net/problem/1076](http://www.acmicpc.net/problem/1076)

#### **풀이:**
1. 저항에 맞는 값을 하나씩 더한 후 마지막 값에 있는 저항에서 10의 index값만큼 제곱을 한 후 출력

#### **코드:**

```
#include <iostream>
#include <string>
#include <math.h>
using namespace std;
string b[10] = { "black", "brown", "red", "orange", "yellow", "green", "blue", "violet", "grey", "white" };
int main(void) {
	string a[3];
	long long temp = 0, go = 0;
	for (int i = 0; i < 3; i++)
		cin >> a[i];
	for (int i = 0; i < 10; i++) {
		if (b[i] == a[0])
			temp += i * 10;
		if (b[i] == a[1])
			temp += i;
		if (b[i] == a[2])
			go += powl(10, i);
	}
	cout << temp * go << endl;
	return 0;
}
```
