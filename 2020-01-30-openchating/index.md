# [프로그래머스]오픈 채팅방

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

카카오톡 오픈채팅방에서는 친구가 아닌 사람들과 대화를 할 수 있는데, 본래 닉네임이 아닌 가상의 닉네임을 사용하여 채팅방에 들어갈 수 있다.



신입사원인 김크루는 카카오톡 오픈 채팅방을 개설한 사람을 위해, 다양한 사람들이 들어오고, 나가는 것을 지켜볼 수 있는 관리자창을 만들기로 했다. 채팅방에 누군가 들어오면 다음 메시지가 출력된다.



[닉네임]님이 들어왔습니다.



채팅방에서 누군가 나가면 다음 메시지가 출력된다.



[닉네임]님이 나갔습니다.



채팅방에서 닉네임을 변경하는 방법은 다음과 같이 두 가지이다.



- 채팅방을 나간 후, 새로운 닉네임으로 다시 들어간다.
- 채팅방에서 닉네임을 변경한다.



닉네임을 변경할 때는 기존에 채팅방에 출력되어 있던 메시지의 닉네임도 전부 변경된다. 



예를 들어, 채팅방에 Muzi와 Prodo라는 닉네임을 사용하는 사람이 순서대로 들어오면 채팅방에는 다음과 같이 메시지가 출력된다.



Muzi님이 들어왔습니다.
 Prodo님이 들어왔습니다.



채팅방에 있던 사람이 나가면 채팅방에는 다음과 같이 메시지가 남는다.



Muzi님이 들어왔습니다.
 Prodo님이 들어왔습니다.
 Muzi님이 나갔습니다.



Muzi가 나간후 다시 들어올 때, Prodo 라는 닉네임으로 들어올 경우 기존에 채팅방에 남아있던 Muzi도 Prodo로 다음과 같이 변경된다.



Prodo님이 들어왔습니다.
 Prodo님이 들어왔습니다.
 Prodo님이 나갔습니다.
 Prodo님이 들어왔습니다.



채팅방은 중복 닉네임을 허용하기 때문에, 현재 채팅방에는 Prodo라는 닉네임을 사용하는 사람이 두 명이 있다. 이제, 채팅방에 두 번째로 들어왔던 Prodo가 Ryan으로 닉네임을 변경하면 채팅방 메시지는 다음과 같이 변경된다.



Prodo님이 들어왔습니다.
 Ryan님이 들어왔습니다.
 Prodo님이 나갔습니다.
 Prodo님이 들어왔습니다.



채팅방에 들어오고 나가거나, 닉네임을 변경한 기록이 담긴 문자열 배열 record가 매개변수로 주어질 때, 모든 기록이 처리된 후, 최종적으로 방을 개설한 사람이 보게 되는 메시지를 문자열 배열 형태로 return 하도록 solution 함수를 완성하라.



# 풀이:

문자열을 공백을 기준으로 분리한다.

첫번째 문자열이 Enter 이거나 Change라면 두번째 문자열인 id에 매칭되어있는 닉네임을 세번째 문자열로 교체해준다.

다시 맨 처음으로 가서 공백을 기준으로 분리한 후 id에 매칭되어있는 닉네임을 string에 저장한다.

첫번째 문자열이 Enter라면, string에 "님이 들어왔습니다." 를 추가한다.

첫번째 문자열이 Leave라면, string에 "님이 나갔습니다." 를 추가한다.

만들어진 string을 answer에 push한다. 



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <sstream>
#include <map>
using namespace std;

vector<string> solution(vector<string> record) {	
	vector<string> answer;
	map<string, string> m;
	vector<vector<string>> r(record.size(), vector<string>(3));
	for (int i = 0; i < record.size(); i++) {
		stringstream c(record[i]);
		c >> r[i][0];
		c >> r[i][1];
		if (r[i][0] == "Enter" || r[i][0] == "Change") {
			c >> r[i][2];
			m[r[i][1]] = r[i][2];
		}
	}
	for (int i = 0; i < record.size(); i++) {
		string s = m[r[i][1]];
		if (r[i][0] == "Enter")
			s += "님이 들어왔습니다.";
		else if (r[i][0] == "Leave")
			s += "님이 나갔습니다.";
		else
			continue;
		answer.push_back(s);
	}
    return answer;
}
```

