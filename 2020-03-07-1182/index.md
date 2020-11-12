# [백준]1182 부분수열의 합

https://www.acmicpc.net/problem/1182

# 풀이:

N개의 정수로 이루어진 수열을 a라고 했을 때,

a의 부분수열을 모두 탐색하여 그 합이 S가 되는 갯수를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int N, S, a[22], s = 0;
void B(int x, int y) {
	if (x > -1 && y == S)	s++;
	while(++x < N)	B(x, y + a[x]);
}
int main() {
	cin >> N >> S;
	for (int i = 0; i < N; i++)		cin >> a[i];
	B(-1, 0);
	cout << s << endl;
}
```

