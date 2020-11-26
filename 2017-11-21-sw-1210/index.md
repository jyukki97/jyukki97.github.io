# [sw]사다리


https://www.swexpertacademy.com/main/code/problem/problemDetail.do?contestProbId=AV14ABYKADACFAYh&

# **풀이:**
1. int[100][100] 배열에 사다리를 저장
2. 사다리 끝에 있는 도착점을 찾음
3. 사다리 위로 올라가며 옆에 길이 있나 확인
4. 맨 위에 x값을 출력

# **코드:**

```c++
#include <iostream>
#include <string>
using namespace std;

int lineup(int n[100][100], int yc, int xc, bool left, bool right) {
	if (yc == 0)
		return xc;
	if (xc > 0 && right == false && n[yc][xc - 1] == 1)
		return lineup(n, yc, xc - 1,true,false);
	else if (xc < 99 && left==false && n[yc][xc + 1] == 1)
		return lineup(n, yc, xc + 1,false,true);
	else
		return lineup(n, yc - 1, xc,false,false);
}
int main(void) {
	for (int t = 1; t < 11; t++) {
		int a;
		cin >> a;
		int line[100][100];
		int count;
		for (int i = 0; i < 100; i++) {
			for (int y = 0; y < 100; y++) {
				cin >> line[i][y];
			}
		}
		for (int i = 0; i < 100; i++) {
			if (line[99][i] == 2) {
				count = i;
				break;
			}
		}
		cout << "#" << t << " " << lineup(line, 98, count, false, false) << endl;
	}
	return 0;
}
}
```


