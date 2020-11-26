# [백준]1351 무한 수열


[https://www.acmicpc.net/problem/1351](http://www.acmicpc.net/problem/1351)

# **풀이:**
1. N번째 수열부터 차례대로 찾아나간다.
2. N번째 수열이 map 에 존재한다면 그대로 리턴, 없다면 N = a/b + a/c 로 돌아가서 찾기
3. N이 0이라면 1을 리턴
4. 각각의 값이 매우 크므로 long long 사용
5. 실패 코드 예시처럼 map을 쓰지않고 리턴을 할 경우 같은 수열이 여러번 중복되어 계산되기 때문에 시간초과가 날 수 있다.


# **코드:**
사용언어 : c++

```c++
#include <iostream>
#include <map>
using namespace std;
long long a, b, c;
map<long long, long long> n;
long long infi(long long q) {
	if (q == 0)
		return 1;
	if (n.count(q / b) == 0) {
		n.insert(make_pair(q / b, infi(q / b)));
	}
	if (n.count(q / c) == 0) {
		n.insert(make_pair(q / c, infi(q / c)));
	}
	return n.at(q / b) + n.at(q / c);
}
int main(void) {
	cin >> a >> b >> c;
	cout << infi(a) << endl;
	return 0;
}	
```



# **실패 코드:**
사용언어 : c++

```c++
#include <iostream>
using namespace std;
double a, b, c;
double infi(double q) {
	if (q == 0)
		return 1;
	return infi(q / b) + infi(q / c);
}
int main(void) {
	cin >> a >> b >> c;
	cout << infi(a) << endl;
	return 0;
}	
```


