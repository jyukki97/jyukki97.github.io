# [백준]17266 어두운 굴다리


https://www.acmicpc.net/problem/17266

# 풀이:

가로등들의 사이 길이 / 2 가 가장 긴 것을 찾는다.



단, 첫 가로등과 마지막 가로등은 왼쪽 끝과 오른쪽 끝에 가로등이 없기 때문에 /2를 하지않는다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
using namespace std;

int main() {
	int n, m, i, x, v[100001], c = 0, d = 0, s, f = 1;
	
	cin >> n >> m;
	fill(v, v + n + 1, 0);
	for (i = 0; i < m; i++) {
		cin >> x;
		v[x] = 1;
	}

	for (i = 0; i <= n; i++) {
		if (v[i]) {
			if (f) s = i, f = 0;
			else s = s > (i - d + 1) / 2 ? s : (i - d + 1) / 2;
			d = i;
		}
		if (i == n) s = s > i - d ? s : i - d;
	}
	cout << s << endl;
}
```
