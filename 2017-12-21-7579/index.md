# [백준]7579 앱


[https://www.acmicpc.net/problem/7579](http://www.acmicpc.net/problem/7579)

# **풀이:**
1. 처음 문제를 풀때는 DP[메모리]로 풀었더니 시간초과가 났다.
2. 그래서 DP[c]로 풀게되었다.
3. 가격이 0이고 메모리가 0인 지점부터
4. 하나하나 더해가면서 만들어나간다.
5. 그 후 가격이 낮은 곳부터 검사하면서 메모리가 M값보다 높아지면 출력한다.
6. iter = a.end(); 를 처음에 iter = a.begin(); 으로 했을 때 출력이 잘못되는 것을 발견하였다.
7. 아마 작은 값부터 더해가는 과정에 겹치는 값이 생겼을 것이라고 본다.

# **코드:**

```c++
#include <iostream>
#include <map>
#include <algorithm>
using namespace std;
map<int, int> a;
int k[101], c[101];
int main(void) {
	int n, m, size, temp;
	cin >> n >> m;
	a[0] = 0;
	for (int i = 0; i < n; i++)
		cin >> k[i];
	for (int i = 0; i < n; i++)
		cin >> c[i];
	map<int, int>::iterator iter;
	for (int i = 0; i < n; i++) {
		size = a.size();
		iter = a.end();
		iter--;
		for (int t = 0; t < size; t++, iter--)
			a[iter->first + c[i]] = max(a[iter->first + c[i]], a[iter->first] + k[i]);
	}
	for (iter = a.begin(); iter != a.end(); ++iter) {
		if (iter->second >= m) {
			temp = iter->first;
			break;
		}
	}
	cout << temp << endl;
	return 0;
}
```

# **시간 초과 코드:**

```c++
#include <iostream>
#include <map>
#include <algorithm>
using namespace std;
map<int, int> a;
int k[101], c[101];
int main(void) {
	int n, m, size;
	cin >> n >> m;
	for (int i = 0; i < n; i++)
		cin >> k[i];
	for (int i = 0; i < n; i++)
		cin >> c[i];
	for (int i = 0; i < n; i++) {
		map<int, int>::iterator iter;
		size = a.size();
		iter = a.begin();
		for (int t = 0; t < size; t++, ++iter) {
			if (a[iter->first + k[i]] == 0)
				a[iter->first + k[i]] = iter->second + c[i];
			else
				a[iter->first + k[i]] = min(a[iter->first + k[i]], iter->second + c[i]);
		}
		if (a[k[i]] == 0)
			a[k[i]] = c[i];
		else
			a[k[i]] = min(a[k[i]],c[i]);
	}
	int temp = 2147483647;
	map<int, int>::iterator iter;
	for (iter = a.begin(); iter != a.end(); ++iter) {
		if (iter->first >= m)
			temp = min(iter->second, temp);
	}
	cout << temp << endl;
	return 0;
}
```

