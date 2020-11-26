# 1947 선물 전달

[https://www.acmicpc.net/problem/1947](http://www.acmicpc.net/problem/1947)

#### **풀이:**
1. a[i]
	: i명이 선물을 나눠갖는 경우의 수
2. a[i - 1] * (i - 1)
	: i번 째 사람이 i - 1 번째 사람의 선물을 골랐을 경우
2. a[i - 2] * (i - 1)
	: i번 째 사람이 i - 1 번째 사람의 선물을 고르지 않았을 경우
    
#### **주의사항:**
1. a[1] 일 때 즉, 1명 일 때 경우의 수가 아무것도 하지않는 것 1개일줄 알았으나 0개로 취급.
2. 너무 큰 수가 계산되므로 주어진 수로 나눈 나머지를 출력한다.

#### **코드:**

```
#include <iostream>
using namespace std;
long long a[1000010] = { 0,0,1,2 };
int main(void) {
	int n;
	cin >> n;
	for (int i = 4; i <= n; i++) {
		a[i] = ((i - 1) * (a[i - 1] + a[i - 2]))% 1000000000;
	}
	cout << a[n] << endl;
	return 0;
}
```
