# [백준]10816 숫자 카드2

https://www.acmicpc.net/problem/10816

# 풀이:

배열에 숫자 카드들을 넣는다.

배열을 정렬한다.

몇 개 가지고 있는지 구해야 할 카드를 k 라고 할 때,

 

k가 최초로 나오는 위치 = lower_bound,

k보다 큰 값이 최초로 나오는 위치 = upper_bound

로 구할 수 있다.

즉 upper_bound - lower_bound를 실행한다면 답을 구할 수 있다.



###### cout과 cin 을 쓰면 시간초과가 나므로 주의하자.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, k, a[500001];
int main() {
	scanf("%d", &n);
	for (int i = 0; i < n; i++)
		scanf("%d", &a[i]);
	sort(a, a + n);
	scanf("%d", &m);
	for (int i = 0; i < m; i++) {
		scanf("%d", &k);
		auto l = lower_bound(a, a + n, k);
		auto r = upper_bound(a, a + n, k);
		printf("%d ", r - l);
	}
	printf("\n");
	return 0;
}

```

