# [백준]10867 중복 빼고 정렬하기

https://www.acmicpc.net/problem/10867

# 풀이:

N개의 정수를 중복을 제외하고 오름차순으로 정렬하여 출력한다.



# **코드:** 

사용언어 : c++
```c++
#include <iostream>
#include <set>
using namespace std;
int main() {
	int n, a; set<int> s;
	cin >> n;
	while (n--) {cin >> a; s.insert(a);}
	for (auto i : s)	cout << i << " ";
	cout << endl;
}
```

