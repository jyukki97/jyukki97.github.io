# 2579 계단 오르기

+++
author = "jyukki"
categories = ["백준"]
tags = ["algorithm", "C++", "DP"]
date = "2017-11-29"
description = "algorithm"
featured = ""
featuredalt = ""
featuredpath = "date"
linktitle = ""
title = "[백준]2579 계단 오르기"
type = "post"

+++

https://www.acmicpc.net/problem/2579

# **풀이:**
1. b[i][0] 은 i번째를 골랐을 때, i-1번째를 안고른 경우의 수
2. b[i][1] 은 i번째를 골랐을 때, i-1번째를 고른 경우의 수

# **코드:**

```C++
#include <iostream>
#include <algorithm>
using namespace std;

int main(void) {
	int n;
	cin >> n;
	int a[301];
	for (int i = 0; i < n; i++) {
		cin >> a[i];
	}
	int b[301][2] = { a[0],0,a[1],a[0] + a[1],0 };
	for (int i = 2; i < n; i++) {
		for (int t = 0; t < 2; t++) {
			if (t == 0)
				b[i][t] = max(b[i - 2][0], b[i - 2][1]) + a[i];
			if (t == 1)
				b[i][t] = b[i - 1][0] + a[i];
		}
	}
	cout << max(b[n - 1][0], b[n - 1][1]) << endl;
	return 0;
}
```


