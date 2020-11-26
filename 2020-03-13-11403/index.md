# [백준]11403 경로 찾기

https://www.acmicpc.net/problem/11403

# 풀이:

[[C++\]플로이드-와샬 알고리즘(Floyd-Warshall Algorithm)](https://jyukki97.github.io/learn/2020-02-27-floydwarshall/) 참고



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#define F(i,n)for(int i=0;i<n;i++)
using namespace std;
int n, a[102][102];
int main() {
	cin >> n;
	F(i, n)	F(t, n)	cin >> a[i][t];
	F(u, 2) F(i, n)	F(t, n)	F(y, n) if(!a[i][t]) a[i][t] = a[i][y] & a[y][t];
	F(i, n) {
		F(t, n) cout << a[i][t] << " ";
		cout << endl;
	}
}
```

