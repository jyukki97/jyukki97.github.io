# [프로그래머스]스킬트리

[https://programmers.co.kr](https://programmers.co.kr)

# 문제:

선행 스킬이란 어떤 스킬을 배우기 전에 먼저 배워야 하는 스킬을 뜻합니다.



예를 들어 선행 스킬 순서가 `스파크 → 라이트닝 볼트 → 썬더`일때, 썬더를 배우려면 먼저 라이트닝 볼트를 배워야 하고, 라이트닝 볼트를 배우려면 먼저 스파크를 배워야 합니다.



위 순서에 없는 다른 스킬(힐링 등)은 순서에 상관없이 배울 수 있습니다. 따라서 `스파크 → 힐링 → 라이트닝 볼트 → 썬더`와 같은 스킬트리는 가능하지만, `썬더 → 스파크`나 `라이트닝 볼트 → 스파크 → 힐링 → 썬더`와 같은 스킬트리는 불가능합니다.



선행 스킬 순서 skill과 유저들이 만든 스킬트리[1](https://programmers.co.kr/learn/courses/30/lessons/49993#fn1)를 담은 배열 skill_trees가 매개변수로 주어질 때, 가능한 스킬트리 개수를 return 하는 solution 함수를 작성해주세요.



# **풀이:**
유저들이 만든 스킬트리를 처음 부터 살펴본다.

만약 스킬이 선행스킬에 처음에 있다면 선행스킬을 배웠음을 체크한다.

만약 스킬이 선행스킬에 없다면 그냥 배울 수 있으므로 패스한다.

만약 스킬이 선행스킬을 배우지 않은 채 다음 선행스킬에 있다면, 스킬을 배울수 없으므로 반복문을 나간다.

 

# **코드:**
사용언어 : c++
```c++
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>
// 파라미터로 주어지는 문자열은 const로 주어집니다. 변경하려면 문자열을 복사해서 사용하세요.
// skill_trees_len은 배열 skill_trees의 길이입니다.
int solution(const char* skill, const char* skill_trees[], size_t skill_trees_len) {
    int answer = 0;
    for (int i = 0;i < skill_trees_len;i++) {
		bool b = true;
		int c = 0;
		for (int t = 0;t < strlen(skill_trees[i]);t++) {
			if (skill_trees[i][t] == skill[c])
				c++;
			else {
				for (int y = c + 1;y < strlen(skill);y++) {
					if (skill_trees[i][t] == skill[y]) {
						b = false;
						break;
					}
				}
			}
		}
		if (b)
			answer++;
	}
    return answer;
}
```

