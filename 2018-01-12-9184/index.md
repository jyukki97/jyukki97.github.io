# 9184 신나는 함수 실행

[https://www.acmicpc.net/problem/9184](http://www.acmicpc.net/problem/9184)

#### **풀이:**
1. DP함수가 주어져 있으므로 메모이제이션을 하면된다.
2. 단, a, b, c 의 최대 크기가 주어져있지않으므로 20이 넘어간 값은 생략하도록한다.
3. -1, -1, -1 이 입력으로 들어올 경우 루프를 끝날 수 있게 만든다.

#### **코드:**

```
#include <iostream>
#include <string.h>
using namespace std;
int fuc[21][21][21];
int w(int a,int b,int c) {
	if (a <= 0 || b <= 0 || c <= 0)
		return 1;
	if (a > 20 || b > 20 || c > 20)
		return fuc[20][20][20] = w(20, 20, 20);
	if (fuc[a][b][c] > -1)	return fuc[a][b][c];
	if (a < b && b < c)
		return fuc[a][b][c] = w(a, b, c - 1) + w(a, b - 1, c - 1) - w(a, b - 1, c);
	return	fuc[a][b][c] = w(a - 1, b, c) + w(a - 1, b - 1, c) + w(a - 1, b, c - 1) - w(a - 1, b - 1, c - 1);
}
int main(void) {
	int a, b, c;
	memset(fuc, -1, sizeof(fuc));
	while(true){
		cin >> a >> b >> c;
		if (a == -1 && b == -1 && c == -1)
			break;
		cout << "w(" << a << ", " << b << ", " << c << ") = " << w(a, b, c) << endl;
	}
	return 0;
}
```
