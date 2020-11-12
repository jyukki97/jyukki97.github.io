# [프로그래머스]캐시

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

지도개발팀에서 근무하는 제이지는 지도에서 도시 이름을 검색하면 해당 도시와 관련된 맛집 게시물들을 데이터베이스에서 읽어 보여주는 서비스를 개발하고 있다.
 이 프로그램의 테스팅 업무를 담당하고 있는 어피치는 서비스를 오픈하기 전 각 로직에 대한 성능 측정을 수행하였는데, 제이지가 작성한 부분 중 데이터베이스에서 게시물을 가져오는 부분의 실행시간이 너무 오래 걸린다는 것을 알게 되었다.
 어피치는 제이지에게 해당 로직을 개선하라고 닦달하기 시작하였고, 제이지는 DB 캐시를 적용하여 성능 개선을 시도하고 있지만 캐시 크기를 얼마로 해야 효율적인지 몰라 난감한 상황이다.



어피치에게 시달리는 제이지를 도와, DB 캐시를 적용할 때 캐시 크기에 따른 실행시간 측정 프로그램을 작성하시오.



# 풀이:

대소문자 구별을 안하므로 도시를 모두 대문자로 바꿔준다.

배열 a에 들어있는 도시들 중 현재 도시와 같은 이름이 있다면, answer 을 +1 해주고 배열 a에서 현재 도시를 지운다.

만약 배열 a에 현재 도시와 같은 이름이 없다면, answer 을 +5 해준다.

현재 도시의 이름을 배열 a에 넣는다.

배열 a의 사이즈가 캐시 크기보다 크다면, 배열의 맨 처음값을 삭제해준다.



transform(s.begin(), s.end(), s.begin(), ::toupper);

이 부분에서 toupper 부분 앞에 :: 을 빼면 오류가 난다.

이유는 모르겠다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(int cacheSize, vector<string> cities) {
	vector<string> a;
	int answer = 0;
	for (string s : cities) {
		bool b = true;
		transform(s.begin(), s.end(), s.begin(), ::toupper);
		for (int i = 0; i < a.size(); i++) {
			if (s == a[i]){
				answer++;
				b = false;
				a.erase(a.begin() + i);
				break;
			}
		}
		if (b)
			answer += 5;
		a.push_back(s);
		if (a.size() > cacheSize)
			a.erase(a.begin());
	}
    return answer;
}
```

