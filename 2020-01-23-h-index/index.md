# [프로그래머스]H-index

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

H-Index는 과학자의 생산성과 영향력을 나타내는 지표입니다. 어느 과학자의 H-Index를 나타내는 값인 h를 구하려고 합니다. 위키백과[1](https://programmers.co.kr/learn/courses/30/lessons/42747#fn1)에 따르면, H-Index는 다음과 같이 구합니다.



어떤 과학자가 발표한 논문 `n`편 중, `h`번 이상 인용된 논문이 `h`편 이상이고 나머지 논문이 h번 이하 인용되었다면 `h`가 이 과학자의 H-Index입니다.



어떤 과학자가 발표한 논문의 인용 횟수를 담은 배열 citations가 매개변수로 주어질 때, 이 과학자의 H-Index를 return 하도록 solution 함수를 작성해주세요.



# 풀이:

논문 n편을 정렬한다.

1번째 논문이 1보다 크다면 H-index는 1이 된다.

2번째 논문이 2보다 크다면 H-index는 2가 된다.

​								.

​								.

(n - 1) / 2 번째 논문이 (n - 1) / 2 보다 크다면 H-index는 (n - 1) / 2가 된다.

이렇게 반복했을 때, 가장 큰 H-index값을 return한다.



<u>논문의 인용횟수가 100이든 1000이든 H-index는 n값을 넘을 수 없다.</u>





# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int solution(vector<int> citations) {
    int answer = 0;
    int s = citations.size();
    sort(citations.begin(), citations.end());
	for (int i = 0; i <= (s - 1) / 2; i++)
        answer = max(answer, min(citations[i], s - i));
    return answer;
}
```

