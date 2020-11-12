# [백준]2738 행렬 덧셈

https://www.acmicpc.net/problem/2738

# 풀이:

행렬 A와 행렬 B를 더한 행렬을 출력한다.



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int n, m, i, b, a[10005];
int main() {
	for (cin >> n >> m; i < n * m; i++)
		cin >> a[i]; 
	for (i = 0; i < n * m; printf("%d%s", a[i++] + b, i % m ? " " : "\n"))
		cin >> b;
}
```

