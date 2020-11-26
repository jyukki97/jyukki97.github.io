# [프로그래머스]기지국 설치

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

N개의 아파트가 일렬로 쭉 늘어서 있습니다. 이 중에서 일부 아파트 옥상에는 4g 기지국이 설치되어 있습니다. 기술이 발전해 5g 수요가 높아져 4g 기지국을 5g 기지국으로 바꾸려 합니다. 그런데 5g 기지국은 4g 기지국보다 전달 범위가 좁아, 4g 기지국을 5g 기지국으로 바꾸면 어떤 아파트에는 전파가 도달하지 않습니다.



예를 들어 11개의 아파트가 쭉 늘어서 있고, [4, 11] 번째 아파트 옥상에는 4g 기지국이 설치되어 있습니다. 만약 이 4g 기지국이 전파 도달 거리가 1인 5g 기지국으로 바뀔 경우 모든 아파트에 전파를 전달할 수 없습니다. (전파의 도달 거리가 W일 땐, 기지국이 설치된 아파트를 기준으로 전파를 양쪽으로 W만큼 전달할 수 있습니다.)



- 초기에, 1, 2, 6, 7, 8, 9번째 아파트에는 전파가 전달되지 않습니다.



![image](https://res.cloudinary.com/jistring93/image/upload/v1492073407/%EA%B8%B0%EC%A7%80%EA%B5%AD%EC%84%A4%EC%B9%981_pvskxt.png)



- 1, 7, 9번째 아파트 옥상에 기지국을 설치할 경우, 모든 아파트에 전파를 전달할 수 있습니다.



![image](https://res.cloudinary.com/jistring93/image/upload/v1492073617/%EA%B8%B0%EC%A7%80%EA%B5%AD%EC%84%A4%EC%B9%982_kml0pb.png)



- 3개의 아파트보다 더 많은 아파트 옥상에 기지국을 설치할 경우에도 모든 아파트에 전파를 전달할 수 있습니다.



![image](https://res.cloudinary.com/jistring93/image/upload/v1492073725/%EA%B8%B0%EC%A7%80%EA%B5%AD%EC%84%A4%EC%B9%983_xhv7r3.png)



이때, 우리는 기지국을 **최소로 설치**하면서 모든 아파트에 전파를 전달하려고 합니다. 위의 예시에선 최소 3개의 아파트 옥상에 기지국을 설치해야 모든 아파트에 전파를 전달할 수 있습니다.



아파트의 개수 N, 현재 기지국이 설치된 아파트의 번호가 담긴 1차원 배열 stations, 전파의 도달 거리 W가 매개변수로 주어질 때, 모든 아파트에 전파를 전달하기 위해 증설해야 할 기지국 개수의 최솟값을 리턴하는 solution 함수를 완성해주세요



# 풀이:

1번 아파트부터 기지국을 설치해 나간다.

만약 현재 설치하는 아파트에 이미 설치되 있던 기지국 전파가 들어온다면,

기지국 전파가 들어오는 범위에 아파트는 건너뛰고 다시 설치해 나간다.

총 기지국을 몇개 설치 했는지 리턴한다. 



# **코드:**

사용언어 : c++
```c++
#include <iostream>
#include <vector>
using namespace std;

int solution(int n, vector<int> stations, int w)
{
  	int answer = 0, c = 0, i = 1;
	while(i <= n){
		if (i >= stations[c] - w && i <= stations[c] + w) {
			i = stations[c] + w;
			c++;
		}
		else {
			i += 2 * w;
			answer++;
		}
		i++;
	}
    return answer;
}
```

