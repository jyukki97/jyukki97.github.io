# 9251 LCS

[https://www.acmicpc.net/problem/9251](http://www.acmicpc.net/problem/9251)

#### **풀이:**
1. dp[a][b]를 1 ~ a번째 까지의 문자열과 1 ~ b 까지의 문자열로 이루어진 최장 공통 부분수열이라고 하자.
2. a번째 문자와 b번째 문자가 같다면, dp[a - 1][b - 1] 에 1을 더해준다.
3. 즉, dp[a][b] = dp[a - 1][b - 1] + 1  이 된다.
4. a번째 문자와 b번째 문자가 다르다면, a번째 문자를 제거한 문자열과 b번째 문자를 제거한 문자열을 비교하여 최댓값을 받는다.
5. 즉, dp[a][b] = max(dp[a - 1][b], dp[a][b - 1]) 이 된다. 

#### **코드:**
사용언어 : c++
{% highlight c++ %}
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;
int d[1002][1002];
int main(void) {
	string a,b;
	cin >> a >> b;
	for (int i = 0; i < a.length(); i++)
		for (int t = 0; t < b.length(); t++)
			if (a[i] == b[t])
				d[i + 1][t + 1] = d[i][t] + 1;
			else
				d[i + 1][t + 1] = max(d[i + 1][t], d[i][t + 1]);
	cout << d[a.length()][b.length()] << endl;
	return 0;
}
{% endhighlight %}
