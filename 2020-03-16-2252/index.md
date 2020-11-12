# [백준]2252 줄 세우기

https://www.acmicpc.net/problem/2252

# 풀이:

b[i] : i 보다 작은 사람들의 수

b[i] 가 0인 i를 맨 앞에 세운다.

i보다 큰 학생들을 t라고 할 때, b[t] 값을 각각 -1 해준다.

모든 학생들을 세울때까지 반복한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;
int n, m, i, q, w, b[32002], c[32002];
int main() {
	cin >> n >> m;
	vector<vector<int>> a(n + 1);
	vector<int> v;
	for (i = 0; i < m; i++) {
		cin >> q >> w;
		a[q].push_back(w), b[w]++;
	}
	while (v.size() != n)
		for (i = 1; i <= n; i++) 
			if (!b[i] && !c[i]) {
				c[i] = 1, v.push_back(i);
				for (int t : a[i]) b[t]--;
				break;
			}
	for (int t : v)	cout << t << " ";
	cout << endl;
}
```

