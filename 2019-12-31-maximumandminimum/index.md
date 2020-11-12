# [프로그래머스]최댓값과 최솟값

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 (최소값) (최대값)형태의 문자열을 반환하는 함수, solution을 완성하세요.
 예를들어 s가 1 2 3 4라면 1 4를 리턴하고, -1 -2 -3 -4라면 -4 -1을 리턴하면 됩니다.

# 풀이:

공백 문자로 구분된 문자열을 배열안에 구분해서 넣는다.

나눠진 배열을 int 형으로 정렬한다. (string 형으로 정렬할 경우 사전순으로 정렬되기 때문에 안된다.)

배열에 맨 처음값과 마지막값을 리턴해준다.

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

string solution(string s) {
    vector<int> a;
	int c = 0;
	string answer = "";
	for (int i = 0;i < s.size();i++) {
		if (s[i] == ' ') {
			a.push_back(stoi(s.substr(c, i)));
			c = i + 1;
		}
	}
	a.push_back(stoi(s.substr(c, s.size())));
	sort(a.begin(), a.end());
	answer += to_string(a.front());
	answer += " ";
	answer += to_string(a.back());
    return answer;
}
```

