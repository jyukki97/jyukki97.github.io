# [백준]2548 대표 자연수

https://www.acmicpc.net/problem/2548

# 풀이:

정렬한 뒤 가운데에 있는 값을 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, i, a[20005];
int main() {
	cin >> n;
	for (i = 0; i < n; i++) cin >> a[i];
	sort(a, a + n);
	cout << a[(n - 1) / 2] << endl;
}
```

