# [백준]17269 이름궁합 테스트


https://www.acmicpc.net/problem/17269

# 풀이:

이름 두개를 받은 후



글자의 획수를 더하여 한개씩 진행한다.



최종 더한 두 숫자를 출력한다.



# **코드:** 

사용언어 : c++

```c++
#include <iostream>
#include <vector>
using namespace std;

int main() {
	int n, m, i, t, q[26] = {3,2,1,2,4,3,1,3,1,1,3,1,3,2,1,2,2,2,1,2,1,1,1,2,2,1};
	string a, b;
	cin >> n >> m >> a >> b;
	vector<vector<int>> v(1);
	for (i = 0, t = 0;; i++, t++) {
		if (i >= n && t >= m)break;
		if (i < n) v[0].push_back(q[a[i] - 'A']);
		if (t < m) v[0].push_back(q[b[t] - 'A']);
	}
	while (1) {
		vector<int> w;
		for (i = 0; i < v.back().size() - 1; i++) {
			w.push_back((v.back()[i] + v.back()[i + 1]) % 10);
		}
		v.push_back(w);
		if (w.size() == 2) break;
	}
	cout << v.back()[0] * 10 + v.back()[1] << "%" << endl;
}
```
