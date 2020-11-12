# [백준]1015 수열 정렬

https://www.acmicpc.net/problem/1015

# 풀이:

배열 A를 정렬한 배열을 배열 B라고 하자.

현재 위치가 i 일 때, A[i] 값이 배열 B의 어디에 위치해 있는지 찾아서 출력한다.



ex)

A

2 3 1

B

1 2 3

답:

1 2 0



###### 수의 중복이 있을 수 있으므로 주의하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int N, a[52], b[52], d[52], c;
int main(void) {
	cin >> N;
	for (int i = 0; i < N; i++) {
		cin >> a[i];
		b[i] = a[i];
	}
	sort(a, a + N);
	for (int i = 0; i < N; i++) {
		c = lower_bound(a, a + N, b[i]) - a;
		while (d[c])	c++;
		cout << c << " ";
		d[c] = 1;
	}
	cout << endl;
}
```

