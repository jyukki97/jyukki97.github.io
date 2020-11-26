# [백준]2684 동전 게임

https://www.acmicpc.net/problem/2684

# 풀이:

뒤뒤뒤, 뒤뒤앞, 뒤앞뒤, 뒤앞앞, 앞뒤뒤, 앞뒤앞, 앞앞뒤, 앞앞앞 순서대로 공백으로 구분해서 출력한다



# **코드:** 

사용언어 : c++	
```c++
#include <iostream>
using namespace std;
int T, i, a[8]; char c[41];
int main() {
	cin >> T;
	while (T--) {
		fill(a, a + 8, 0);
		for (i = 0; i < 40 ; i++) {
			cin >> c[i];
			if (i > 1) {
				if (c[i - 2] == 84)
					if (c[i - 1] == 84)
						if (c[i] == 84)	a[0]++;
						else a[1]++;
					else
						if (c[i] == 84)	a[2]++;
						else a[3]++;
				else
					if (c[i - 1] == 84)
						if (c[i] == 84)	a[4]++;
						else a[5]++;
					else
						if (c[i] == 84)	a[6]++;
						else a[7]++;
			}
		}
		for (i = 0; i < 8; i++)
			printf("%d ", a[i]);
		printf("\n");
	}
}
```

