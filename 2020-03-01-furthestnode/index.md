# [프로그래머스]가장 먼 노드

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

n개의 노드가 있는 그래프가 있습니다. 각 노드는 1부터 n까지 번호가 적혀있습니다. 1번 노드에서 가장 멀리 떨어진 노드의 갯수를 구하려고 합니다. 가장 멀리 떨어진 노드란 최단경로로 이동했을 때 간선의 개수가 가장 많은 노드들을 의미합니다.



노드의 개수 n, 간선에 대한 정보가 담긴 2차원 배열 vertex가 매개변수로 주어질 때, 1번 노드로부터 가장 멀리 떨어진 노드가 몇 개인지를 return 하도록 solution 함수를 작성해주세요.



# 풀이:

현재 위치를 i 라고 하자.



이때까지 방문을 한적이 없고, i와의 거리가 1차이나는 노드를 배열에 저장한 후 visit을 true로 바꿔준다.



반복도중 배열이 비었다면, 반복을 중지하고, 그 전 배열의 사이즈를 리턴한다.



# **코드:**

사용언어 : c++
```c++
#include <string>
#include <vector>

using namespace std;
int solution(int n, vector<vector<int>> edge) {
    int answer = 0;
    vector<vector<int>> a(n + 1), c;
    vector<bool> b(n + 1);
    for (auto i : edge) {
        a[i[0]].push_back(i[1]);
        a[i[1]].push_back(i[0]);
    }
    c.push_back({ 1 });
    b[1] = true;
   while (1) {
       vector<int> v;
       for (auto i : c.back())
           for (auto t : a[i])
                if (!b[t]) {
                    v.push_back(t);
                    b[t] = true;
                }
       if(v.empty())    break;
       c.push_back(v);
   }
    return c.back().size();
}
```

