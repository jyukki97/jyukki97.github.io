# [프로그래머스]영어 끝말잇기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

1부터 n까지 번호가 붙어있는 n명의 사람이 영어 끝말잇기를 하고 있습니다. 영어 끝말잇기는 다음과 같은 규칙으로 진행됩니다. 



1. 1번부터 번호 순서대로 한 사람씩 차례대로 단어를 말합니다. 
2. 마지막 사람이 단어를 말한 다음에는 다시 1번부터 시작합니다. 
3. 앞사람이 말한 단어의 마지막 문자로 시작하는 단어를 말해야 합니다. 
4. 이전에 등장했던 단어는 사용할 수 없습니다. 
5. 한 글자인 단어는 인정되지 않습니다. 



다음은 3명이 끝말잇기를 하는 상황을 나타냅니다. 



tank → kick → know → wheel → land → dream → mother → robot → tank



위 끝말잇기는 다음과 같이 진행됩니다.



- 1번 사람이 자신의 첫 번째 차례에 tank를 말합니다.
- 2번 사람이 자신의 첫 번째 차례에 kick을 말합니다.
- 3번 사람이 자신의 첫 번째 차례에 know를 말합니다.
- 1번 사람이 자신의 두 번째 차례에 wheel을 말합니다.
- (계속 진행)



끝말잇기를 계속 진행해 나가다 보면, 3번 사람이 자신의 세 번째 차례에 말한 tank 라는 단어는 이전에 등장했던 단어이므로 탈락하게 됩니다. 



사람의 수 n과 사람들이 순서대로 말한 단어 words 가 매개변수로 주어질 때, 가장 먼저 탈락하는 사람의 번호와 그 사람이 자신의 몇 번째 차례에 탈락하는지를 구해서 return 하도록 solution 함수를 완성해주세요.



# 풀이:

배열 words의 첫번째부터 차례대로 확인한다.

만약 현재 단어가 이전에 나온 단어이거나, 바로 전 단어의 마지막 문자와 현재단어의 첫번째 단어가 다르다면 현재 차례의 말한 사람과 이 사람이 몇번째로 말한 단어인지 리턴한다.



# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <iostream>
#include <map>
using namespace std;

vector<int> solution(int n, vector<string> words) {
	map<string, int> a = { {words[0],1} };
	vector<int> answer = { 0,0 };
	for (int i = 1;i < words.size();i++) {
		if (a[words[i]] || words[i].front() != words[i - 1].back()) {
			answer[0] = (i % n) + 1;
			answer[1] = (i / n) + 1;
			break;
		}
		a[words[i]] = 1;
	}
    return answer;
}
```

