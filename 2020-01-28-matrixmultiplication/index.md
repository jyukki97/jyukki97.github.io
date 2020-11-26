# [프로그래머스]행렬의 곱셈

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

2차원 행렬 arr1과 arr2를 입력받아, arr1에 arr2를 곱한 결과를 반환하는 함수, solution을 완성해주세요.



# 풀이:

arr1의 가로행과 arr2의 세로열의 값들을 각각 곱한것을 더한 값을 a에 저장한다.

저장된 배열 a를 answer에 푸쉬 한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;

vector<vector<int>> solution(vector<vector<int>> arr1, vector<vector<int>> arr2) {
    vector<vector<int>> answer;
    for (int i = 0; i < arr1.size(); i++){
        vector<int>a;
        for (int t = 0; t < arr2[0].size(); t++){
            int sum = 0;
            for (int y = 0; y < arr1[0].size(); y++)
                sum += arr1[i][y] * arr2[y][t];
            a.push_back(sum);
        }
        answer.push_back(a);
    }
    return answer;
}
```

