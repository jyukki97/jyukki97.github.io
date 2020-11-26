# [백준]1516 게임 개발

https://www.acmicpc.net/problem/1516

# 풀이:

[[백준\]1005 ACM Craft](https://jyukki97.github.io/blog/2020-03-05-1005/) 참고

# **코드:** 

사용언어 : c++
```c++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
int N, i, q, a[502], b[502];
vector<vector<int>>v;
int A(int x) { 
	if (b[x])	return b[x]; 
	for (int t : v[x])	b[x] = max(b[x], A(t));
	b[x] += a[x]; 
	return b[x]; 
}
int main() {
	cin >> N; 
	v.resize(N + 1);
	for (i = 1; i <= N; i++) { 
		cin >> a[i] >> q; 
		while (q != -1)	v[i].push_back(q), cin >> q; 
	}
	for (i = 1; i <= N; i++)	cout << A(i) << endl;
}
```

