# [프로그래머스]x만큼 간격이 있는 n개의 숫자

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.



# 풀이:

x * 1, x *2...., x * n 을 리턴한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<long long> solution(int x, int n) {
    vector<long long> answer;
	for (int i = 1;i <= n;i++)
        answer.push_back(x * i);
    return answer;
}
```

