# 2749 피보나치 수3

[https://www.acmicpc.net/problem/2749](http://www.acmicpc.net/problem/2749)

#### **풀이:**
1. 코드 설명은 피보나치 코드 참고
2. 참고의 문제와는 다르게 매우 큰 수가 들어온다.
3. 피보나치를 n으로 나누면 주기가 생성되는데 주기로 끊어서 풀도록 한다.
    

#### **코드:**

```
#include <iostream>
using namespace std;
long long a[3] = { 0,1 }, n;
int main() {
	cin >> n;
	for (int i = 2; i <= n % 1500000; i++)
		a[i % 3] = (a[(i - 1) % 3] + a[(i - 2) % 3]) % 1000000;
	cout << a[(n % 1500000) % 3] << endl;
}
```

#### **참고:**
[https://www.acmicpc.net/blog/view/28](https://www.acmicpc.net/blog/view/28)

#### **피보나치 코드:**
[https://jyukki97.github.io/2748](https://jyukki97.github.io/2748)
