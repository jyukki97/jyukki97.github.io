# [프로그래머스]모의고사

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.



1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...
 2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, 2, 1, 2, 3, 2, 4, 2, 5, ...
 3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, ...



1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.



# 풀이:

각각의 수포자들이 찍는 방식대로 모두 탐색한다.

맞춘 갯수의 최댓값을 저장해 놓는다.

최댓값과 맞춘 갯수가 같은 수포자를 answer에 푸쉬한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
using namespace std;

vector<int> solution(vector<int> answers) {
    vector<vector<int>> a = { { 1,2,3,4,5 }, { 2,1,2,3,2,4,2,5 }, { 3,3,1,1,2,2,4,4,5,5 } };
	vector<int> d(3, 0);
	vector<int> answer;
	int m = 0;
	for (int i = 0; i < answers.size(); i++) {
		for (int t = 0; t < 3; t++) {
			if (answers[i] == a[t][i % a[t].size()]) {
				d[t]++;
				m = max(m, d[t]);
			}
		}
	}
	for (int i = 0; i < 3; i++)
		if (d[i] == m)
			answer.push_back(i + 1);
    return answer;
}
```

