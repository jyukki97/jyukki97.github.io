# [백준]1676 팩도리얼 0의 개수

https://www.acmicpc.net/problem/1676

# 풀이:

뒤에서 0이 나오려면 팩토리얼을 곱할때, 5 가 곱해져야한다.



즉, 5의 배수가 지나간다면, 팩토리얼의 갯수가 1씩 늘어날 것이다.



팩토리얼을 만드는 동안 5가 몇번 곱해지는지 계산한다면, 0의 갯수를 구할 수 있다.



(이 문제는 N의 제한이 500 까지이기 때문에, 팩토리얼을 전체 계산해서 구하기는 힘들다.)





# **코드:**

사용언어 : c++
```c++
#include <iostream>
using namespace std;

int main() {
	int n, m = 0;
	cin >> n;
	while (n) {
		n /= 5;
		m += n;
	}
	cout << m << endl;
	return 0;
}
```

