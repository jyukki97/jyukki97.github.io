# 2240 자두나무

[https://www.acmicpc.net/problem/2240](http://www.acmicpc.net/problem/2240)

#### **풀이:**
1. s[t][w]를 자두의 남은 이동수가 w이고, 1 ~ t번째 자두까지 받아먹을 수 있는 최대 갯수
2. t의 숫자를 늘리며 이전 번째 자두수에서 +1을 해준다.
3. 자두나무가 같다면 w를 같게 다르다면 +1해준다.
4. 이때 w가 최대 이동횟수를 넘지않도록 주의한다.
 

#### **코드:**
사용언어 : c++
{% highlight c++ %}
#include <iostream>
#include <algorithm>
using namespace std;
int T, w, a[1002];
int s[1002][32] = { 0 };
int main(void) {
	cin >> T >> w;
	int m = 0;
	a[0] = 1;
	s[0][w] = 1;
	for (int i = 1; i <= T; i++)
		cin >> a[i];
	for (int i = 1; i <= T; i++)
		for (int t = 0; t < i; t++)
			for (int y = 0; y <= w; y++) {
				if (a[i] != a[t] && s[t][y + 1] != 0)
					s[i][y] = max(s[i][y], s[t][y + 1] + 1);
				else if (a[i] == a[t] && s[t][y] != 0)
					s[i][y] = max(s[i][y], s[t][y] + 1);
				m = max(m, s[i][y]);
			}
	cout << m - 1 << endl;
	return 0;
}
{% endhighlight %}
