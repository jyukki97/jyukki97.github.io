# [프로그래머스]제일 작은 수 제거하기

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.



# 풀이:

arr에서 제일 작은 수를 찾아 삭제한다.

만약 arr이 비었다면 -1을 넣는다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>
using namespace std;

vector<int> solution(vector<int> arr) {
    int min = arr[0], c = 0;
    for(int i = 1; i < arr.size(); i++){
        if(min > arr[i]){
            min = arr[i];
            c = i;
        }
    }
    arr.erase(arr.begin() + c);
    if(arr.empty())
        arr.push_back(-1);
    return arr;
}
```

