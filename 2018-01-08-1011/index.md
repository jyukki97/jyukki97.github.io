# 1011 Fly me to the Alpha Centauri

[https://www.acmicpc.net/problem/1011](http://www.acmicpc.net/problem/1011)

#### **풀이:**
1. 거리가 제곱수 일 때(d = s^2), 그 거리 까지 갈 수 있는 최소 작동수에서 최대 거리는 그 수의 제곱근(s) 이다.
2. 최소 작동수는 대칭일때 만들어지므로 제곱수일 때 최소 작동수는 2*s - 1이 된다.
3. 거리가 제곱수가 아니라면, 거리에서 그 거리보다 작은 제곱수를 뺀 나머지로 계산한다.
4. (d - s^2) / s + 1 즉 제곱수 만큼 간 후 남은 거리를 갈 수 있는 최대 거리인 s로 나눈 값에 올림한 값과 같다.

#### **코드:**

```
#include <iostream>
#include <math.h>
using namespace std;
int main(void) {
	int T, x, y;
	cin >> T;
	for (int i = 0; i < T; i++) {
		cin >> x >> y;
		long long temp = 0;
		int s = sqrt(y - x);
		if (s == 1)
			temp += y - x;
		else if ((y - x - s * s) % s == 0)
			temp += 2 * s + (y - x - s * s) / s - 1;
		else
			temp += 2 * s + (y - x - s * s) / s;
		cout << temp << endl;
		}
	return 0;
}
```
