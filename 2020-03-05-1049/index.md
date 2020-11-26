# [백준]1049 기타줄

https://www.acmicpc.net/problem/1049

# 풀이:

여러 브랜드 중 6줄 패키지 가격의 최솟값과 낱개 가격의 최솟값을 저장해 놓는다.

 

낱개 * 6 보다 패키지 가격이 더 높다면, 패키지로 살 이유가 없으므로 낱개 가격을 출력한다.

필요한 줄의 갯수가 6개 이하라면, 낱개 가격과 패키지 가격 중 낮은 가격을 출력한다.

둘 다 아니라면, (전체를 패키지로 사는 것) 과 (6개로 나눠지는 만큼 패키지로 사고 나머지는 낱개로 사는 것) 둘 중 낮은 가격을 출력한다.





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int N, M, q, w, a = 1001, b = 1001, dp[102] = { 0 };
int main(void) {
	cin >> N >> M;
	for (int i = 0; i < M; i++) {
		cin >> q >> w;
		a = min(a, q);
		b = min(b, w);
	}
	for (int i = 1; i <= N; i++) {
		dp[i] = (((i - 1) / 6) + 1) * a;
		dp[i] = min(dp[i], dp[i - 1] + b);
	}
	cout << dp[N] << endl;
}
```



# 코드:

사용언어 : c++

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int N, M, q, w, a = 1001, b = 1001;
int main(void) {
	cin >> N >> M;
	for (int i = 0; i < M; i++) {
		cin >> q >> w;
		a = min(a, q);
		b = min(b, w);
	}
	if (N <= 6)		cout << min(a, b * N) << endl;
	else if (b * 6 < a)	cout << b * N << endl;
	else	cout << min((((N - 1) / 6) + 1) * a, (N / 6) * a + (N % 6) * b) << endl;
}
```


