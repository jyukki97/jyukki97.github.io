# [백준]2957 이진 탐색 트리


[https://www.acmicpc.net/problem/2957](http://www.acmicpc.net/problem/2957)

# **풀이:**
1. 트리의 루트에서 부터 왼쪽 오른쪽에 삽입할때 마다 높이를 1씩 증가시켜 준다.
2. cin , cout을 사용할 경우 시간초과가 나므로 scanf, printf 를 사용하도록 하자
3. 출력의 사이즈가 int 사이즈를 넘어가므로 long long 을 사용하자

# **코드:**

```c++
#include <iostream>
#include <map>
#include <algorithm>
#include <stdio.h>
using namespace std;
int main(void) {
	int n, num;
	cin >> n;
	map<int, long long int> a;
	a[300001] = -1;
	a[0] = -1;
	long long temp = 0;
	for (int i = 0; i < n; i++) {
		scanf_s("%d", &num);
		a[num] = max((--a.lower_bound(num))->second, a.upper_bound(num)->second) + 1;
		temp += a[num];
		printf_s("%lld\n", temp);
	}
	return 0;
}
```


