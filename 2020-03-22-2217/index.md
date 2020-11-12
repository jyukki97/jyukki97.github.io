# [백준]2217 로프

https://www.acmicpc.net/problem/2217

# 풀이:

a[i] : i 무게를 들 수 있는 로프의 갯수

로프의 중량보다 가벼운 물체는 들 수 있으므로 중량보다 낮은 값은 전부 +1 씩 해준다.

a[i] * i 의 값이 가장 높은 값을 출력한다. 

i 무게를 들 수 있는 로프의 갯수가 a[i] 개 일 때, a[i] 개의 로프를 이용하여 중량이 a[i] * i 인 물체를 들 수 있기 때문에)



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
using namespace std;
int n, m, i, s = 0, a[10002];
int main() {
	cin >> n;
	while (n--) {
		cin >> m;
		while (m) a[m--]++;
	}
	for (i = 1; i < 10001; i++)	s = s < i * a[i] ? i * a[i] : s;
	cout << s << endl;
}
```

