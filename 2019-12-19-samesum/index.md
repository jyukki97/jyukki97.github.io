# [프로그래머스]같은 숫자는 싫어

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. 배열 arr에서 연속적인 숫자는 하나를 제외하고 모두 삭제한 배열을 리턴한다.

# **코드:**
사용언어 : c++
```c++
#include <vector>
#include <iostream>

using namespace std;

vector<int> solution(vector<int> arr) 
{
    vector<int> answer;
	for (int i : arr) {
		if (answer.size() > 0) {
			if (answer.back() != i) {
				answer.push_back(i);
			}
		}
		else {
			answer.push_back(i);
		}
	}
    return answer;
}
```

