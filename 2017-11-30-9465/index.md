# 9465 스티커

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
title = "[백준]9465 스티커"
type = "post"

+++

[https://www.acmicpc.net/problem/9465](http://www.acmicpc.net/problem/9465)

# **풀이:**
1. a[i][t] 는 i행 t열의 스티커를 골랐을 때 최대 점수
2. a[t][i] += max(a[(t + 1) % 2][i - 2], a[(t + 1) % 2][i - 1])

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;
int a[2][100001] = { 0 };
int main(void) {
	int T,n;
	cin >> T;
	for (int y = 0; y < T; y++) {
		cin >> n;
		for (int t = 0; t < 2; t++) {
			for (int i = 0; i < n; i++) {
				cin >> a[t][i];
			}
		}
		for (int i = 1; i < n; i++) {
			for (int t = 0; t < 2; t++) {
				a[t][i] += max(a[(t + 1) % 2][i - 2], a[(t + 1) % 2][i - 1]);
			}
		}
		cout << max(a[0][n - 1], a[1][n - 1]) << endl;
	}
}
```


