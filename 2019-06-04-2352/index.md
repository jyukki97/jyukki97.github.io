# [백준]2352 반도체 설계

[https://www.acmicpc.net/problem/2352](http://www.acmicpc.net/problem/2352)

# **풀이:**
1. 맨 처음 값부터 하나 하나 입력받는다.
2. 입력받은 값이 벡터 안에 있는 값들 보다 크다면 벡터에 맨 뒤에 넣는다.
3. 벡터의 처음부터 검색했을 때, 입력받은 값보다 큰 값이 있다면, 그 값과 교체한다.
4. 벡터의 원소 갯수를 출력한다.
5. 일반적으로 for문을 두개 쓴 O(n^2)의 코드는 시간초과가 나므로 주의하자

# **코드:**
사용언어 : c++
```c++
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
vector<int>d;
int main(void) {
	int n, s, l;
	cin >> n;
	while(n--) {
		cin >> s;
		l = lower_bound(d.begin(), d.end(), s) - d.begin();
		if (l == d.size())
			d.push_back(s);
		else
			d[l] = s;
	}
	cout << d.size() << endl;
	return 0;
}
```



# **시간 초과 코드:**
사용언어 : c++
    

```c++
#include <iostream>
#include <algorithm>
using namespace std;
int s[40001], d[40001], r = 0;
int main(void) {
	int n;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> s[i];
		for (int t = 0; t < i; t++) {
			if (s[i] > s[t])
				d[i] = max(d[i], d[t]);
		}
		d[i]++;
		r = max(r, d[i]);
	}
	cout << r << endl;
	return 0;
}
```


