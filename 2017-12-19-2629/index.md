# [백준]2629 양팔저울


[https://www.acmicpc.net/problem/2629](http://www.acmicpc.net/problem/2629)

# **풀이:**
1. 양팔저울에 추를 매달아 구할 수 있는 무게를 알아내는 문제
2. 양팔저울에 한 곳에 놓았을 때, 양쪽에 서로 따로 놓았을 때 두 가지의 경우가 있다.
3. 이 때 같이놓으면 + 따로 놓은것은 -로 놓고 배열에 저장한다.
4. 구슬의 무게에 맞는 배열의 값이 1이면 구할 수 있고, 1이 아닌경우 구할 수 없는 것으로 취급한다.

# **코드:**

```c++
#include <iostream>
#include <map>
#include <vector>
using namespace std;
map<int, int> a;
vector<int> b;
int main(void) {
	int n, temp, k, size;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> temp;
		map<int, int>::iterator iter;
		size = a.size();
		iter = a.begin();
		for (int t = 0; t < size; t++) {
			b.push_back(iter->first + temp);
			b.push_back(temp - iter->first);
			b.push_back(iter->first - temp);
			iter++;
		}
		a[temp] = 1;
		while (b.size() != 0) {
			a[b.back()] = 1;
			b.pop_back();
		}
	}
	cin >> k;
	for (int i = 0; i < k; i++) {
		cin >> temp;
		if (a[temp] == 1)
			cout << "Y ";
		else
			cout << "N ";
	}
	cout << endl;
	return 0;
}
```

