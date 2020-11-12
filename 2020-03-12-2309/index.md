# [백준]2309 일곱 난쟁이

https://www.acmicpc.net/problem/2309

# 풀이:

아홉 난쟁이의 키의 합을 S라고 하자.



아홉 난쟁이 중 랜덤으로 뽑은 두 명의 키의 합을 T라고 하자.



S - T = 100 이라면



뽑은 두 난쟁이를 제외하고 오름차순으로 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int a[9], i, t, s = 0;
int main() {
	for (i = 0; i < 9; i++) {
		cin >> a[i];
		s += a[i];
	}
	sort(a, a + 9);
	for (i = 0; i < 9; i++) {
		for (t = i + 1; t < 9; t++)	if (s - a[i] - a[t] == 100)	break;
		if (s - a[i] - a[t] == 100)	break;
	}
	for (s = 0; s < 9; s++)	if (s != i && s != t)	cout << a[s] << endl;
}
```

