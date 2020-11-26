# 2011 암호코드

[https://www.acmicpc.net/problem/2011](http://www.acmicpc.net/problem/2011)

#### **풀이:**
1. dp[a]를 a자리 까지 숫자를 암호화 할 수 있는 가짓수 라고 하자.
2. (a - 1) * 10 + a 가 10~26 사이라면 dp[a] = dp[a - 1] + dp[a - 2] 가 된다.
3. 10~26 사이가 아니라면, dp[a] = dp[a - 1] 이 된다.
4. 이 때, a 가 0 이라면, 암호를 해석 할 수 없으므로 0을 출력한다. (이 때, (a - 1 * 10 + a) 가 10 ~ 26 사이라면 가능하므로 주의하자)
5. 정답이 매우 클 수 있으므로, 1000000으로 나눈 나머지를 출력한다.
6. 1번째 자리의 숫자가 0이라면 무조건 암호가 잘못되어 있으므로 0을 출력한다.

#### **코드:**
사용언어 : c++
{% highlight c++ %}
#include <iostream>
#include <string.h>
using namespace std;
int d[5002] = { 1, 1 };
int main(void) {
	char n[5001];
	cin >> n;
	for (int i = 2; i <= strlen(n); i++) {
		if (n[i - 1] == '0')
			d[i - 1] = 0;
		d[i] = d[i - 1];
		if (n[i - 2] == '1' || (n[i - 2] == '2' && n[i - 1] < '7'))
			(d[i] += d[i - 2]) %= 1000000;
	}
	if (n[0] == '0')
		cout << 0 << endl;
	else
		cout << d[strlen(n)] << endl;
	return 0;
}
{% endhighlight %}
