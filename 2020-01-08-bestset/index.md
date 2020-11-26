# [프로그래머스]최고의 집합

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

자연수 n 개로 이루어진 중복 집합(multi set, 편의상 이후에는 집합으로 통칭) 중에 다음 두 조건을 만족하는 집합을 최고의 집합이라고 합니다.



1. 각 원소의 합이 S가 되는 수의 집합
2. 위 조건을 만족하면서 각 원소의 곱 이 최대가 되는 집합



예를 들어서 자연수 2개로 이루어진 집합 중 합이 9가 되는 집합은 다음과 같이 4개가 있습니다.
 { 1, 8 }, { 2, 7 }, { 3, 6 }, { 4, 5 }
 그중 각 원소의 곱이 최대인 { 4, 5 }가 최고의 집합입니다.



집합의 원소의 개수 n과 모든 원소들의 합 s가 매개변수로 주어질 때, 최고의 집합을 return 하는 solution 함수를 완성해주세요.



# 풀이:

s 가 n 보다 작다면 자연수의 합으로 나타낼 수 없으므로 -1을 리턴한다.

아니라면, answer 배열에 s / n을 넣는다. (각 원소의 곱이 최대가 되려면 각 원소의 차이가 최소이어야하므로)

넣은 수만큼 s를 빼주고 n 또한 -1 해준다.

n이 0이될때까지 반복한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<int> solution(int n, int s) {
    vector<int> answer;
   	int a;
	int c = 0;
	if (s < n)	answer.push_back(-1);
    else{
        answer.resize(n);
		while (n) {
			a = s / n;
			answer[c] = a;
			s -= a;
			n--;
			c++;
		}
    }
    return answer;
}
```

