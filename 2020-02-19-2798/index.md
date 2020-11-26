# [백준]2798 블랙잭

https://www.acmicpc.net/problem/2798

# 풀이:

3장을 뽑을 수 있는 모든 경우의 수를 확인하여 3장의 합이 M값을 넘지않는 최댓값을 출력한다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() { 
	int n, m, ma = 0;
	cin >> n >> m;
	vector<int> a(n, 0);
	for (int i = 0; i < n; i++)
		cin >> a[i];
	for (int i = 0; i < n - 2; i++)
		for (int t = i + 1; t < n - 1; t++)
			for (int y = t + 1; y < n; y++)
				if (a[i] + a[t] + a[y] <= m)
					ma = max(ma, a[i] + a[t] + a[y]);
	cout << ma << endl;
	return 0;
}
```

