# [백준]2501 약수 구하기

https://www.acmicpc.net/problem/2501

# 풀이:

n의 약수들 중 k번째로 작은 수를 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, k, i, c = 0;
int main() {
	cin >> n >> k;
	for (i = 1; i <= n; i++)
		if (!(n % i)) {
			k--;
			if (!k) {
				c = i;
				break;
			}
		}
	cout << c << endl;
}
```

