# [백준]1759 암호 만들기

https://www.acmicpc.net/problem/1759

# 풀이:

C개의 문자들을 사전순으로 정렬한다.



정렬된 문자열을 L개만큼 출력한다. 



단, 최소 한 개의 모음과 두개의 자음이 있어야한다.

증가하는 순서로 있어야한다.





# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
using namespace std;
int n, m, i, b[20]; char c[20], d[20];
void P(int x, int z) {
	if (x == n) {
		int y = 0, t = 0, r = 0;
		for (; y < x; y++)
			if (d[y] == 'a' || d[y] == 'e' || d[y] == 'i' 
                || d[y] == 'o' || d[y] == 'u')	t++;
			else r++;
		if(t && r>1)	cout << d << endl;
		return;
	}
	for (int y = z; y < m; y++)	
        if (!b[y])	b[y] = 1, d[x] = c[y], P(x + 1, y + 1), b[y] = 0;
}
int main() {
	cin >> n >> m;
	for (; i < m; i++)	cin >> c[i];
	sort(c, c + m);
	P(0, 0);
}
```

