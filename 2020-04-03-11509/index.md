# [백준]11509 풍선 맞추기

https://www.acmicpc.net/problem/11509

# 풀이:

풍선의 높이를 확인한다.



현재 풍선의 높이가 H(i) 라고 하자.

H(i) + 1 인 풍선이 현재 풍선 앞에 나타난적이 있다면, H(i) + 1 높이의 풍선을 -1 해준다.

나타난적이 없다면, 화살을 새로 써야 하므로 화살의 갯수를 +1 해준다.



화살의 갯수를 출력한다.



# **코드:** 

사용언어 : c	
```c++
#include <iostream>
using namespace std;
int n, i, a, b[1000005], c;
int main() {
	cin >> n;
	for (i = 0; i < n; i++, b[a]++, b[a + 1] ? b[a + 1]-- : c++)	cin >> a;
	cout << c << endl;
}
```

