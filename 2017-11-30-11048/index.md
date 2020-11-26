# 11048 이동하기

+++
author = "jyukki"
categories = ["백준"]
tags = ["algorithm", "C++", "DP"]
date = "2017-11-30"
description = "algorithm"
featured = ""
featuredalt = ""
featuredpath = "date"
linktitle = ""
title = "[백준]11048 이동하기"

+++

[https://www.acmicpc.net/problem/11048](http://www.acmicpc.net/problem/11048)

# **풀이:**
1. a[i][t] 는 i행 t열로 갈 때 사탕의 최대 갯수
2. a[i][t] 는 위에서 올때와 왼쪽에서 올때 중 최대값으로 구할 수 있다.
3. a[i][t] += max(a[i - 1][t], a[i][t - 1]);

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;
int a[1002][1002] = { 0 };
int main(void) {
	int n, m;
	cin >> n >> m;
	for (int i = 1; i <= n; i++) {
		for (int t = 1; t <= m; t++) {
			cin >> a[i][t];
		}
	}
	for (int i = 1; i <= n; i++) {
		for (int t = 1; t <= m; t++) {
			a[i][t] += max(a[i - 1][t], a[i][t - 1]);
		}
	}
	cout << a[n][m] << endl;
	return 0;
}
```


