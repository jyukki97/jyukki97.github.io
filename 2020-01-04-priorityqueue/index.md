# [프로그래머스]이중우선순위큐

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

이중 우선순위 큐는 다음 연산을 할 수 있는 자료구조를 말합니다.



| 명령어 | 수신 탑(높이)                  |
| ------ | ------------------------------ |
| I 숫자 | 큐에 주어진 숫자를 삽입합니다. |
| D 1    | 큐에서 최댓값을 삭제합니다.    |
| D -1   | 큐에서 최솟값을 삭제합니다.    |



이중 우선순위 큐가 할 연산 operations가 매개변수로 주어질 때, 모든 연산을 처리한 후 큐가 비어있으면 [0,0] 비어있지 않으면 [최댓값, 최솟값]을 return 하도록 solution 함수를 구현해주세요.

# 풀이:

첫 영어가 I 라면 뒤에 숫자를 삽입한다.

첫 영어가 D이고, 뒤 문자가 1이라면 최댓값을 삭제한다.

첫 영어가 D이고, 뒤 문자가 -1이라면 최솟값을 삭제한다.

삽입된 숫자가 없다면 {0, 0}을 리턴한다.

삽입된 숫자가 있다면 그 중 {최댓값, 최솟값} 을 리턴한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <map>
using namespace std;

vector<int> solution(vector<string> operations) {
   	multimap<int, int> a;
	for (int i = 0;i < operations.size();i++)
		if (operations[i][0] == 'I')
			a.insert(pair<int,int>(stoi(operations[i].substr(2, operations[i].size() - 1)) , 1));
		else if(a.size() && operations[i] == "D 1")
			a.erase(a.rbegin()->first);
		else if (a.size() && operations[i] == "D -1")
			a.erase(a.begin()->first);
	if (!a.size())
		return {0, 0};
	else
		return {a.rbegin()->first, a.begin()->first};
}
```

