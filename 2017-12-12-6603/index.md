# [백준]6603 로또


[https://www.acmicpc.net/problem/6603](http://www.acmicpc.net/problem/6603)

# **풀이:**
1. N 개의 로또 번호 중 6개를 선택하여 로또를 만드는 프로그램
2. 6개의 번호를 사전순으로 하나씩 선택하면서 출력한다.
3. 출력 사이사이에 빈칸을 만들어주고, 하나의 테스트 케이스가 끝나면 빈 줄을 하나 출력한다.
4. 0이 출력되면 끝나므로 while 문 안에 if문으로 제한을 넣어준다.

# **코드:**

```c++
#include <iostream>
using namespace std;
int a[13];
int main(void) {
	while (true) {
		int n;
		cin >> n;
		if (n == 0)
			break;
		for (int i = 0; i < n; i++) {
			cin >> a[i];
		}
		int b[6] = { 0,1,2,3,4,5 };
		while (true) {
			cout << a[b[0]] << " " << a[b[1]] 
				<< " " << a[b[2]] << " " << a[b[3]] << " " << a[b[4]] 
				<< " " << a[b[5]] << endl;
			if (b[0] >= n - 6)
				break;
			else if (b[1] >= n - 5) {
				b[0]++;
				for (int i = 0; i < 5; i++) {
					b[i + 1] = b[i] + 1;
				}
			}
			else if (b[2] >= n - 4) {
				b[1]++;
				for (int i = 1; i < 5; i++) {
					b[i + 1] = b[i] + 1;
				}
			}
			else if (b[3] >= n - 3) {
				b[2]++;
				for (int i = 2; i < 5; i++) {
					b[i + 1] = b[i] + 1;
				}
			}
			else if (b[4] >= n - 2) {
				b[3]++;
				for (int i = 3; i < 5; i++) {
					b[i + 1] = b[i] + 1;
				}
			}
			else if (b[5] >= n - 1) {
				b[4]++;
				b[5] = b[4] + 1;
			}
			else
				b[5]++;
		}
		cout << endl;
	}
	return 0;
}
```


