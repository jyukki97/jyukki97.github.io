# [프로그래머스]프린터

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

일반적인 프린터는 인쇄 요청이 들어온 순서대로 인쇄합니다. 그렇기 때문에 중요한 문서가 나중에 인쇄될 수 있습니다. 이런 문제를 보완하기 위해 중요도가 높은 문서를 먼저 인쇄하는 프린터를 개발했습니다. 이 새롭게 개발한 프린터는 아래와 같은 방식으로 인쇄 작업을 수행합니다.



```
1. 인쇄 대기목록의 가장 앞에 있는 문서(J)를 대기목록에서 꺼냅니다.
2. 나머지 인쇄 대기목록에서 J보다 중요도가 높은 문서가 한 개라도 존재하면 J를 대기목록의 가장 마지막에 넣습니다.
3. 그렇지 않으면 J를 인쇄합니다.
```



예를 들어, 4개의 문서(A, B, C, D)가 순서대로 인쇄 대기목록에 있고 중요도가 2 1 3 2 라면 C D A B 순으로 인쇄하게 됩니다.



내가 인쇄를 요청한 문서가 몇 번째로 인쇄되는지 알고 싶습니다. 위의 예에서 C는 1번째로, A는 3번째로 인쇄됩니다.



현재 대기목록에 있는 문서의 중요도가 순서대로 담긴 배열 priorities와 내가 인쇄를 요청한 문서가 현재 대기목록의 어떤 위치에 있는지를 알려주는 location이 매개변수로 주어질 때, 내가 인쇄를 요청한 문서가 몇 번째로 인쇄되는지 return 하도록 solution 함수를 작성해주세요.



# **풀이:**
현재 대기 목록의 있는 문서 중 맨 앞에 문서가 전체 문서 중 중요도가 제일 높다면 인쇄한다.

만약 전체 문서 중 중요도가 더 큰 문서가 있다면 대기목록 가장 맨 뒤로 이동시킨다.

이 작업을 반복하다가 location 값에있는 위치에 문서가 인쇄된다면 반복을 중지하고, 몇번째로 인쇄되었는지 리턴한다.

 

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(vector<int> priorities, int location) {
    int first = 0;
	int c = 0;
	while (1) {
		for (int i = first + 1;i < priorities.size();i++) {
			if (priorities[first] < priorities[i]) {
				priorities.push_back(priorities[first]);
				if (location == first) {
					location = priorities.size() - 1;
				}
				c--;
				break;
			}
		}
		c++;
		if (location == first)
			break;
		first++;	
	}
    return c;
}
```

