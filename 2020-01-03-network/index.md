# [프로그래머스]네트워크

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

네트워크란 컴퓨터 상호 간에 정보를 교환할 수 있도록 연결된 형태를 의미합니다. 예를 들어, 컴퓨터 A와 컴퓨터 B가 직접적으로 연결되어있고, 컴퓨터 B와 컴퓨터 C가 직접적으로 연결되어 있을 때 컴퓨터 A와 컴퓨터 C도 간접적으로 연결되어 정보를 교환할 수 있습니다. 따라서 컴퓨터 A, B, C는 모두 같은 네트워크 상에 있다고 할 수 있습니다.



컴퓨터의 개수 n, 연결에 대한 정보가 담긴 2차원 배열 computers가 매개변수로 주어질 때, 네트워크의 개수를 return 하도록 solution 함수를 작성하시오.



# 풀이:

A 컴퓨터부터 확인한다. 확인했다면 visit[A]를 1로 바꾼다.

A 컴퓨터가 B컴퓨터와 이어져있다면 B로 간다 .... 반복한다.

더이상 이어져있는 컴퓨터가 없다면 네트워크의 갯수를 1더해준다.

모든 컴퓨터를 확인한 후 네트워크의 갯수를 리턶나다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int d(int x, vector<vector<int>> c, vector<int>& a) {
	if (a[x]) return 0;
	a[x] = 1;
	for (int i = 0;i < a.size();i++)
		if (c[x][i] && i != x)
			d(i, c, a);
	return 1;
}
int solution(int n, vector<vector<int>> computers) {
    vector<int> a(n, 0);
    int answer = 0;
	for (int i = 0;i < n;i++) {
		answer += d(i, computers, a);
	}
    return answer;
}
```

