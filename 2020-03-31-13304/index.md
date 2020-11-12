# [백준]13304 방 배정

https://www.acmicpc.net/problem/13304

# 풀이:

1, 2학년인 학생들

3,4 학년이면서 남학생

3,4 학년이면서 여학생

5,6 학년이면서 남학생

5,6 학년이면서 여학생

으로 나누어 방을 배정한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int n, k, q, w, a[5];
int main() {
	cin >> n >> k;
	while (n--) {
		cin >> q >> w;
		if (w < 3) a[0]++;
		else if (w < 5)
			if (q)	a[1]++;
			else a[2]++;
		else
			if (q) a[3]++;
			else a[4]++;
	}
	for (q = 0, w = 0; q < 5; q++)
		w += a[q] / k + (a[q] % k ? 1 : 0);
	cout << w << endl;
}
```

