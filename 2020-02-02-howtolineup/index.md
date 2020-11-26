# [프로그래머스]줄 서는 방법

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

n명의 사람이 일렬로 줄을 서고 있습니다.  n명의 사람들에게는 각각 1번부터 n번까지 번호가 매겨져 있습니다. n명이 사람을 줄을 서는 방법은 여러가지 방법이 있습니다. 예를 들어서 3명의 사람이 있다면 다음과 같이 6개의 방법이 있습니다.



- [1, 2, 3]
- [1, 3, 2]
- [2, 1, 3]
- [2, 3, 1]
- [3, 1, 2]
- [3, 2, 1]



사람의 수 n과, 자연수 k가 주어질 때, 사람을 나열 하는 방법을 사전 순으로 나열 했을 때, k번째 방법을 return하는 solution 함수를 완성해주세요.



# 풀이:

1 ~ n 까지의 숫자를 저장한 배열을 만든다.

저장한 배열의 (k - 1) / (n - 1)! 번째 숫자를 answer에 push한다.

저장한 숫자를 배열에서 지운다.

k를 (n - 1)! 로 나눈 나머지로 바꾼다.

n을 -1 해준다.



```c++
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1
```

 각 자릿수를 n이라고 했을 때, (맨 오른쪽을 1이라고 한다.)

각 자릿수의 값은 (n - 1)! 마다 변하게 된다.

즉 (n - 1)! 의 배수를 확인한다면 맨 앞자리를 구할 수 있다.

그 후 맨 앞자리를 없앤 후 계속 반복한다면 k번째 방법을 구할 수 있다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
using namespace std;

vector<int> solution(int n, long long k) {
    vector<int> answer;
    vector<int> a;
    long long m = 1;
    for(int i = 1; i <= n; i++){
        a.push_back(i);
        m *= i;
    }
    while(n){
        m /= n;
        long long num = !k ? n - 1 : (k - 1) / m;
        answer.push_back(a[num]);
        a.erase(a.begin() + num);
        k %= m;
        n--;
    }
    return answer;
}
```

