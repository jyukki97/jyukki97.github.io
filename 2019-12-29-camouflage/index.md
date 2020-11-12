# [프로그래머스]위장

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

스파이들은 매일 다른 옷을 조합하여 입어 자신을 위장합니다.



예를 들어 스파이가 가진 옷이 아래와 같고 오늘 스파이가 동그란 안경, 긴 코트, 파란색 티셔츠를 입었다면 다음날은 청바지를 추가로 입거나 동그란 안경 대신 검정 선글라스를 착용하거나 해야 합니다.



| 종류 | 이름                       |
| ---- | -------------------------- |
| 얼굴 | 동그란 안경, 검정 선글라스 |
| 상의 | 파란색 티셔츠              |
| 하의 | 청바지                     |
| 겉옷 | 긴 코트                    |



스파이가 가진 의상들이 담긴 2차원 배열 clothes가 주어질 때 서로 다른 옷의 조합의 수를 return 하도록 solution 함수를 작성해주세요.



# **풀이:**

각 옷들의 종류에 + 1 한것을 곱한 후 1을 빼준다.

예를들어 옷이 3종류라면, (A + 1)(B + 1)(C + 1) - 1 이 답이 된다. 

  

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <map>
using namespace std;

int solution(vector<vector<string>> clothes) {
	int answer = 1;
	map<string, int> a;
	for (int i = 0;i < clothes.size();i++)
		a[clothes[i][1]]++;
	for (auto i = a.begin();i != a.end();i++)
		answer *= i->second + 1;
    return answer-1;
}
```



# **시간초과 코드:**

사용언어 : c++

```c++
#include <vector>
#include <string>
#include <map>
using namespace std;

vector<map<string, string>> a;

void cl(map<string,string> m, int loc, vector<vector<string>> c) {
	a.push_back(m);
	for (int i = loc + 1;i < c.size();i++) {
		if (m.find(c[i][1]) == m.end()) {
			m.insert(pair<string,string>(c[i][1], c[i][0]));
			cl(m, i, c);
			m.erase(c[i][1]);
		}
	}
}

int solution(vector<vector<string>> clothes) {
	int l = 0;

	while (l!=clothes.size()) {
		map<string, string> b;
		b.insert(pair<string,string>(clothes[l][1], clothes[l][0]));
		cl(b, l, clothes);
		l++;
	}
    
    return a.size();
}
```
