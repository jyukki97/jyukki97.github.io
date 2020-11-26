# 14501 퇴사

[https://www.acmicpc.net/problem/14501](http://www.acmicpc.net/problem/14501)

#### **풀이:**
1. 남은일이 N일 일때, M일의 상담을 완료하는데 걸리는 기간을 T(M)라고 가정한다.
2. 1일에 상담을 했다면 할 수 있는 상담은 1+T(1) ~ N 까지가 있다.
3. 1+T(1) 일에 상담을 했다면 할 수 있는 삼담은 1 + T(1) + T(1+T(1) ~ N 까지가 있다.
4. N을 넘지않도록 주의하며 반복한 후 받을 수 있는 금액에 최대를 출력한다.
 

#### **코드:**
사용언어 : c++
{% highlight c++ %}
#include <iostream>
using namespace std;
int a, b[16], c[16];
int ts(int q) {
	int max = 0;
	for (int i = q; i < a; i++) {
		int w = c[i] + ts(i + b[i]);
		if (i + b[i] > a)
			w = 0;
		max = max > w ? max : w;
	}
	return max;
}
int main(void) {
	cin >> a;
	for (int i = 0; i < a; i++)
		cin >> b[i] >> c[i];
	cout << ts(0) << endl;
	return 0;
}
{% endhighlight %}
