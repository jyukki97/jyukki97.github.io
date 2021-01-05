# [백준]17269 이름궁합 테스트


https://www.acmicpc.net/problem/17269

# 풀이:

[[백준\]2624]: https://jyukki97.github.io/2018-01-11-2624/	"[백준\]2624 참고"



# **코드:** 

사용언어 : c++

```c++
#include<iostream>
using namespace std;
long long d[10005] = { 1,1 }, n, m, i;
int main() {
	cin >> n >> m;
	for (i = 2; i <= n; i++)
		d[i] = (d[i - 1] + (i - m >= 0 ? d[i - m] : 0)) % 1000000007;
	cout << d[n] << endl;
}
```
