# [프로그래머스]숫자 야구

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

숫자 야구 게임이란 2명이 서로가 생각한 숫자를 맞추는 게임입니다. [게임해보기](https://scratch.mit.edu/projects/131352991/)



각자 서로 다른 1~9까지 3자리 임의의 숫자를 정한 뒤 서로에게 3자리의 숫자를 불러서 결과를 확인합니다. 그리고 그 결과를 토대로 상대가 정한 숫자를 예상한 뒤 맞힙니다.



```
* 숫자는 맞지만, 위치가 틀렸을 때는 볼
* 숫자와 위치가 모두 맞을 때는 스트라이크
* 숫자와 위치가 모두 틀렸을 때는 아웃
```



예를 들어, 아래의 경우가 있으면



```
A : 123
B : 1스트라이크 1볼.
A : 356
B : 1스트라이크 0볼.
A : 327
B : 2스트라이크 0볼.
A : 489
B : 0스트라이크 1볼.
```



이때 가능한 답은 324와 328 두 가지입니다.



질문한 세 자리의 수, 스트라이크의 수, 볼의 수를 담은 2차원 배열 baseball이 매개변수로 주어질 때, 가능한 답의 개수를 return 하도록 solution 함수를 작성해주세요.



# 풀이:

123 부터 987 까지 모든 경우의 수를 완전 탐색한다.

이 때, 숫자에 0이 들어가거나 222처럼 중복되는 단어가 들어가면 안되므로 제외시켜준다.

현재 숫자와 주어진 숫자들을 3자리 모두 비교하여 숫자와 위치가 모두 같다면 스트라이크를 1 더하고, 숫자가 같으나 위치가 다르다면 볼을 1 더해준다.

만약, 스트라이크와 볼이 주어진 숫자와 같다면 true를 배정한다.

현재 숫자와 주어진 숫자들을 모두 비교했을 때, true값이 있다면 가능한 숫자이므로, answer값을 1 올려준다. 

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

int solution(vector<vector<int>> baseball) {
    int answer = 0;
	for (int i = 123;i <= 987;i++) {
		string a = to_string(i);
		bool c = true;
		if (a[0] == a[1] || a[0] == a[2] || a[1] == a[2] || a[0] == '0' || a[1] == '0' || a[2] == '0')
			continue;
		for (int t = 0;t < baseball.size();t++) {
			string b = to_string(baseball[t][0]);
			int strike = 0;
			int ball = 0;
			for (int y = 0; y < 3; y++) {
				for (int u = 0;u < 3;u++) {
					if (a[y] == b[u]) {
						if (y == u)
							strike++;
						else
							ball++;
					}
				}
			}
			if (strike != baseball[t][1] || ball != baseball[t][2]) {
				c = false;
				break;
			}
		}
		if (c)
			answer++;
	}
    return answer;
}
```

