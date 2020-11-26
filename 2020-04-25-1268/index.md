# [백준]1268 임시 반장 정하기

https://www.acmicpc.net/problem/1268

# 풀이:

현재 상태에서 제일 많은 학생수를 S, 그 학생수를 가진 학생을 C라고 하자.

1번 학생이 몇 명의 학생과 같은 반을 했었는지를 저장하고, 

그 값이 S보다 많다면 S를 교체하고 C에 1을 저장한다.

.

.

.

n번 학생이 몇 명의 학생과 같은 반을 했었는지를 저장하고, 

그 값이 S보다 많다면 S를 교체하고 C에 n을 저장한다.



전체를 다 탐색 한 후 C를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, i, t, y, d, s, c, a[1005][5], b[1005][1005];
int main() {
	cin >> n;
	for (; i < n; i++) for (t = 0; t < 5; t++) cin >> a[i][t];
	for (i = 0; i < n; i++, d = 0) {
		for (t = 0; t < 5; t++)
			for (y = 0; y < n; y++)
				if (a[i][t] == a[y][t])d += !b[i][y], b[i][y] = 1;
		if (s < d)	s = d, c = i;
	}
	cout << c + 1 << endl;
}
```

