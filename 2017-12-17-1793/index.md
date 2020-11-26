# [백준]1793 타일링


[https://www.acmicpc.net/problem/1793](http://www.acmicpc.net/problem/1793)

# **풀이:**

[11727 2XN 타일링2](https://jyukki97.github.io/1965/)

1. DP는 링크와 같으므로 링크를 참고
2. 링크의 코드와 다르게 int 보다 큰 값을 출력해야하므로 어려움이 있다.
3. vector를 사용하여 int를 한자리수 씩 계산하는 방법으로 풀었다.
4. 만약 자릿수의 값이 10보다 커지면 다음 자릿수의 값을 그만큼 올려주는 식으로 풀었다.

# **코드:**

```c++
#include <iostream>
#include <vector>
using namespace std;
vector<int> a[251];
int main(void) {
	int	n, temp;
	int cnt = 3;
	a[0].push_back(1);
	a[1].push_back(1);
	a[2].push_back(3);
	while(cin >> n){
		if (a[n].size() == 0) {
			for (int t = cnt; t < n + 1; t++) {
				int carry = 0;
				for (int y = 0; y < a[t - 2].size(); y++) {
					temp = 2 * a[t - 2][y] + a[t - 1][y] + carry;
					if (temp >= 10) {
						carry = temp / 10;
						temp %= 10;
						a[t].push_back(temp);
						if (y == a[t - 2].size() - 1) {
							if (a[t - 1].size() > a[t - 2].size())
								a[t].push_back(carry + a[t - 1][y + 1]);
							else
								a[t].push_back(carry);
						}
					}
					else {
						a[t].push_back(temp);
						carry = 0;
					}
				}
			}
		}
		for (int y = a[n].size() - 1; y >= 0; y--) {
			cout << a[n][y];
		}
		cout << endl;
		cnt = n + 1;
	}
	return 0;
}
```
