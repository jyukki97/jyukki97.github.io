# [백준]1236 성 지키기

https://www.acmicpc.net/problem/1236

# 풀이:

각 행에 경비병이 있는지 없는지 탐색한다.

경비병이 없는 행의 갯수를 Sn이라고 하자.



각 열에 경비병이 있는지 없는지 탐색한다.

경비병이 없는 열의 갯수를 Sm이라고 하자.



각 행과 열에는 경비병이 1명씩은 있어야 하므로



Sn과 Sm 중 최댓값을 출력한다.





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, t, a[55], b[55], q, w; char c;
int main() {
	cin >> n >> m;
	for (; i < n; i++)
		for (t = 0; t < m; t++) {
			cin >> c;
			if (c == 'X')	q+=!a[i],a[i]=1,w+=!b[t],b[t]=1;
		}
	n -= q, m -= w;
	printf("%d", n < m ? m : n);
}
```

