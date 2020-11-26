# [백준]2959 거북이

https://www.acmicpc.net/problem/2959

# 풀이:

거북이가 만들 수 있는 가장 큰 직사각형의 면적을 출력한다



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[4], i = 4;
int main() {
	while (i--)	cin >> a[i];
	sort(a, a + 4);
	cout << a[0] * a[2] << endl;
}
```

