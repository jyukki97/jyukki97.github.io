# [백준]1931 회의실배정

https://www.acmicpc.net/problem/1931

# 풀이:

회의 정보를 배열에 저장한다.



저장된 배열을 끝나는 시간을 기준으로 정렬한다. (끝나는 시간이 같다면, 시작하는 시간을 기준으로 정렬)



배열을 처음부터 순회해간다.



저장된 끝값보다 현재 시작시간이 더 크다면, 끝값을 현재 끝나는 시간으로 바꾸고 사용할 수 있는 회의 수를 +1 해준다.



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int n, ma = 0, e = -1;

int main() {
	cin >> n;
	vector<pair<int, int>> v(n);
	for (int i = 0; i < n; i++)
		cin >> v[i].second >> v[i].first;
	sort(v.begin(), v.end());
	for (int i = 0; i < n; i++)
		if (e <= v[i].second) {
			e = v[i].first;
			ma++;
		}
	cout << ma << endl;
	return 0;
}
```

