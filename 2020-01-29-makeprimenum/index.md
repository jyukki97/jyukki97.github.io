# [프로그래머스]소수 만들기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

주어진 숫자 중 3개의 수를 더했을 때 소수가 되는 경우의 개수를 구하려고 합니다. 숫자들이 들어있는 배열 nums가 매개변수로 주어질 때, nums에 있는 숫자들 중 서로 다른 3개를 골라 더했을 때 소수가 되는 경우의 개수를 return 하도록 solution 함수를 완성해주세요.



# 풀이:

3개의 숫자를 더한 값이 소수인지 아닌지 판별 후 소수라면 answer을 +1 해준다.



# **코드:**

사용언어 : c++
```c++
#include <vector>
#include <iostream>
#include <math.h>
using namespace std;

int solution(vector<int> nums) {
    int answer = 0;
    for(int i = 0;i < nums.size() - 2;i++)
        for(int t = i + 1;t < nums.size() - 1;t++)
            for(int y = t + 1;y < nums.size();y++){
                bool b = true;
                for(int u = 2;u <= sqrt(nums[i] + nums[t] + nums[y]);u++){
                    if((nums[i] + nums[t] + nums[y]) % u == 0){
                        b = false;
                        break;
                    }
                }
                if(b)   answer++;
            }
    return answer;
}
```

