# [프로그래머스]전화번호 목록

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

전화번호부에 적힌 전화번호 중, 한 번호가 다른 번호의 접두어인 경우가 있는지 확인하려 합니다.
 전화번호가 다음과 같을 경우, 구조대 전화번호는 영석이의 전화번호의 접두사입니다.



- 구조대 : 119
- 박준영 : 97 674 223
- 지영석 : 11 9552 4421



전화번호부에 적힌 전화번호를 담은 배열 phone_book 이 solution 함수의 매개변수로 주어질 때, 어떤 번호가 다른 번호의 접두어인 경우가 있으면 false를 그렇지 않으면 true를 return 하도록 solution 함수를 작성해주세요.



# **풀이:**

phone_book 에 있는 전화번호들을 사전순으로 정렬해 놓는다.

전화번호부에 모든 전화번호를 비교한다.

만약, 현재 보고있는 전화번호가 다음 전화번호의 접두어라면 답을 false로 바꾸고 반복문을 나간다.

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

bool solution(vector<string> phone_book) {
    bool answer = true;
    sort(phone_book.begin(), phone_book.end());
	for (int i = 0;i < phone_book.size() - 1;i++) {
		if (phone_book[i] == phone_book[i+1].substr(0, phone_book[i].size())) {
			answer = false;
			break;
		}
	}
    return answer;
}
```

