# [백준]1806 부분합

https://www.acmicpc.net/problem/1806

# 풀이:

a[i] : 0 ~ i 번째 수 까지의 합

a[i] 와 a[t] 로 시작한다.

a[t] - a[i] 가 S 보다 크거나 같다면, t - i 길이의 부분합이 S 이상이 됨을 알 수 있다.

t를 1 줄이고 한번 더 반복한다.

만약, a[t] - a[i] 가 S 보다 작다면, i++, t++ 해준다.

t값이 N보다 커질때까지 반복한다.

구한 길이를 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int N, S, i, t, s = 0, a[100005];
int main() {
	cin >> N >> S;
	for (i = 1; i <= N; i++) {
		cin >> t;
		a[i] = a[i - 1] + t;
	}
	for (i = 0, t = N; t <= N;)
		if (a[t] - a[i] >= S)	s = t - i, t--;
		else i++,t++;
	cout << s << endl;
}
```

