# [프로그래머스]나누어 떨어지는 숫자 배열

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. arr의 각 원소 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 리턴한다.
2. 만약 배열의 원소가 없다면 -1을 리턴한다. 

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

vector<int> solution(vector<int> arr, int divisor) {
    vector<int> answer;
    for (int i : arr) {
		if (i % divisor == 0)
			answer.push_back(i);
	}
	sort(answer.begin(), answer.end());
    if(answer.size()==0)
        answer.push_back(-1);
    return answer;
}
```

