# [프로그래머스]k번째 수

[https://programmers.co.kr](https://programmers.co.kr)

# **풀이:**
1. array 배열의 commands[0]번째부터 commands[1]번째 까지 자른 후 정렬한다.
2. 자른 배열의 commands[2] 번째 숫자를 출력한다.
3. commands 배열의 길이만큼 반복한다.

# **코드:**
사용언어 : c++
```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

vector<int> solution(vector<int> array, vector<vector<int>> commands) {
    vector<int> answer;
    for(int i=0;i<commands.size();i++){
        vector<int> a = array;
        sort(a.begin()+commands[i][0]-1,a.begin()+commands[i][1]);
        answer.push_back(a[commands[i][0] + commands[i][2] - 2]);    
    }
    return answer;
}
```

