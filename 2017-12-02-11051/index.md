# [백준]11051 이항계수2


[https://www.acmicpc.net/problem/11051](http://www.acmicpc.net/problem/11051)

# **풀이:**
1. nCk 를 나타내는 함수 Comb() 를 만든다.
2. 재귀함수의 특성상 시간초과 때문에 배열에 값을 저장해놓는다.


# **참고: [1010 다리놓기](https://jyukki97.github.io/1010/)**
# **코드:**

```c++
#include <iostream>
using namespace std;
long long cnt[1001][1001] = { 0 };
int Comb(int n, int r) {
	if (r == 0 || r == n)
		return 1;
	else if (r == n - 1 || r == 1)
		return n;
	if (cnt[n - 1][r] == 0)
		cnt[n - 1][r] = Comb(n - 1, r);
	if (cnt[n - 1][r - 1] == 0)
		cnt[n - 1][r - 1] = Comb(n - 1, r - 1);
	return (cnt[n - 1][r] % 10007 + cnt[n - 1][r - 1] % 10007) % 100007;
}
int main(void) {
	int n, k;
	cin >> n >> k;
	cout << Comb(n, k) % 10007<< endl;
	return 0;
}
```


