# [프로그래머스]소수 찾기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

한자리 숫자가 적힌 종이 조각이 흩어져있습니다. 흩어진 종이 조각을 붙여 소수를 몇 개 만들 수 있는지 알아내려 합니다.



각 종이 조각에 적힌 숫자가 적힌 문자열 numbers가 주어졌을 때, 종이 조각으로 만들 수 있는 소수가 몇 개인지 return 하도록 solution 함수를 완성해주세요.



# 풀이:

문자열 numbers로 만들 수 있는 모든 순열을 set에 넣는다. (중복된 숫자를 거르기 위함)

set에 들어있는 수들을 모두 순회하여 소수라면 answer값을 +1 해준다.



(맨 처음에 sort를 하지않을 경우 실패가 뜨는데 왜 그런지는 잘 모르겠다.)



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <set>
#include <algorithm>
using namespace std;

int solution(string numbers) {
    int answer = 0;
	set<int>a;
    sort(numbers.begin(),numbers.end());
	do {
		for (int i = 1; i <= numbers.size(); ++i) 
			a.insert(stoi(numbers.substr(0, i)));
	} while (next_permutation(numbers.begin(), numbers.end()));
	for (set<int>::iterator ite = a.begin(); ite != a.end(); ite++) {
		bool b = true;
		for (int i = 2; i <= sqrt(*ite); i++) {
			if (!(*ite % i)) {
				b = false;
				break;
			}
		}
		if (*ite != 0 && *ite != 1 && b)	answer++;
	}
    return answer;
}
```

