# 1660 캡틴 이다솜

[https://www.acmicpc.net/problem/1660](http://www.acmicpc.net/problem/1660)

#### **풀이:**
1. b[i]
	: i개의 대포알의 개수로 만들 수 있는 사면체의 최소 개수
2. a[i]
	: 사면체의 사이즈가 i인 대포알의 개수
3. b[i] = min(b[i], b[num - a[i]] + 1)

#### **주의사항:**
1. 시간초과에 유의하여 메모이제이션을 하도록한다.
2. min함수를 사용하므로 초기값을 매우 크게 잡아주는 것을 잊지말자.

#### **코드:**

```
#include <iostream>
#include <algorithm>
using namespace std;
int a[200] = { 0 }, b[300010] = { 0 }, q = 1;
int	cap(int num) {
	if (num <= 0 )	return 0;
	if (b[num])	return b[num];
	b[num] = 300000;
	for (int i = q; i > 0; i--) {
		if (a[i] <= num)
			b[num] = min(b[num], cap(num - a[i]) + 1);
	}
	return b[num];
}
int main(void) {
	int n, cnt = 1;
	cin >> n;
	while(true) {
		a[q] = a[q - 1] + cnt;
		cnt += q + 1;
		if (a[q] > n)
			break;
		q++;
	}
	cout << cap(n) << endl;
	return 0;
}
```
