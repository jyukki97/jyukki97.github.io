# [프로그래머스]숫자 블록

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

그렙시에는 0으로 된 도로에 숫자 블록을 설치하기로 하였습니다. 숫자 블록의 규칙은 다음과 같습니다.



블록의 번호가 n 일 때, 가장 처음 블록은 n * 2번째 위치에 설치합니다. 그다음은 n * 3, 그다음은 n * 4, ...로 진행합니다.만약 기존에 블록이 깔려있는 자리라면 그 블록을빼고 새로운 블록으로 집어넣습니다.



예를 들어 1번 블록은 2,3,4,5, ... 인 위치에 우선 설치합니다. 그다음 2번 블록은 4,6,8,10, ... 인 위치에 설치하고, 3번 블록은 6,9,12... 인 위치에 설치합니다.



이렇게 3번 블록까지 설치하고 나면 첫 10개의 블록은 0, 1, 1, 2, 1, 3, 1, 2, 3, 2이됩니다.



그렙시는 길이가 1,000,000,000인 도로에 1번 블록부터 시작하여 10,000,000번 블록까지 위의 규칙으로 모두 놓았습니다.



그렙시의 시장님은 특정 구간의 어떤 블록이 깔려 있는지 알고 싶습니다.



구간을 나타내는 두 수 begin, end 가 매개변수로 주어 질 때, 그 구간에 깔려 있는 블록의 숫자 배열(리스트)을 return하는 solution 함수를 완성해 주세요.



# 풀이:

begin 부터 end 까지 순회한다.

i가 소수라면 1을 푸쉬한다.

i가 1이라면 0을 푸쉬한다.

i가 둘 다 아니라면, i의 약수 중 i를 제외한 최댓값을 푸쉬한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

vector<int> solution(long long begin, long long end) {
    vector<int> answer;
    for(long long i = begin; i <= end; i++){
        int n = 0;
        for(long long t = 2; t <= sqrt(i); t++)
            if(!(i % t)){
                n = i / t;
                break;
            }
        if(i != 1 && !n)
            n = 1;
        answer.push_back(n);
    }
    return answer;
}
```

