# [백준]1062 가르침

https://www.acmicpc.net/problem/1062

# 풀이:

a ~ z 중에 K개의 글자를 배웠을 떄,

N개의 단어 중 몇개의 단어를 읽을 수 있는지 구한 후 그것들 중 최댓값을 출력한다.



###### a, c, i, n, t 다섯개의 글자는 무조건 들어가므로 넣고 시작하자.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int N, K, b, c = 0, d, f;
vector<string> a;
void T(int x, int y) {
	if (y == K) {
		d = 0;
		for (int i = 0; i < N; i++) {
			f = 1;
			for (char s : a[i])	if (!((1 << (s - 'a')) & b)) 	f = 0;
			if (f)	d++;
		}
		c = max(c, d);
	}
	for (int i = x + 1; i < 26; i++)
		if (!((1 << i) & b)) {
			b |= (1 << i);
			T(i, y + 1);
			b &= ~(1 << i);
		}
}
int main() {
	cin >> N >> K;
	a.resize(N);
	for (int i = 0; i < N; i++)	cin >> a[i];
	b |= ((1 << 0) + (1 << 2) + (1 << 13) + (1 << 8) + (1 << 19));
	T(0, 5);
	cout << c << endl;
}
```

