# [백준]15657 N과 M (8)

https://www.acmicpc.net/problem/15657

# 풀이:

수열을 배열에 저장한다.

비내림차순으로 출력해야 하므로 배열을 정렬한다.

현재 배열에 있는 수를 새로운 배열에 옮겨 담는다.

옮긴 수가 M개가 된다면 출력하고,  다른 수를 담는다.

모든 수를 사전 순으로 출력했다면 종료한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, a[8], b[8];
void N(int x, int y) {
	if (!y) {
		for (int i = 0; i < m; i++)	printf("%d ", b[i]);
		printf("\n");
		return;
	}
	for (int i = x; i < n; i++) b[m - y] = a[i], N(i, y - 1);
}

int main() {
	cin >> n >> m;
	for (int i = 0; i < n; i++) cin >> a[i];
	sort(a, a + n);
	N(0, m);
}
```

