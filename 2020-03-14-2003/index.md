# [백준]2003 수들의 합 2

https://www.acmicpc.net/problem/2003

# 풀이:

A[i] 부터 A[j] 까지 하나씩 더해가는 값을 s라고 하자.

만약, s가 m과 같다면, 경우의 수를 +1 해준다.

만약, s가 m보다 크다면, i를 1 더해주고, 다시 반복한다.

i가 n이 될때까지 반복 후 경우의 수를 출력해준다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, t, a[10002], s, c = 0;
int main() {
	scanf("%d%d",&n,&m);
	for (i = 0; i < n; i++)	scanf("%d",&a[i]);
	for (i = 0; i < n; i++) {
		s = 0;
		for (t = i; t < n; t++) {
			s += a[t];
			if (s == m) c++;
			if (s >= m)	break;
		}
	}
	printf("%d\n",c);
}
```

