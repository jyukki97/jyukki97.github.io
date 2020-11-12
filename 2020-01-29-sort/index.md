# [C++]정렬

정렬 ( sort )

```c++
#include<algorithm>
```

사용하기 위해서는 algorithm을 include해준다.



기본적인 사용법은 이렇게된다.

```c++
sort(a.begin(), a.end());
```



기본적인 방식은 오름차순 정렬이다. 



정렬의 방식을 바꾸기 위해서는 다음과 같은 방식을 사용한다.

```c++
sort(a.begin(), a.end(), compare);
```

이 때, compare 함수는 따로 만들어 주어야한다.



예를들어

내림차 순으로 정렬하기 위해서는

```c++
bool compare(int a, int b){
	return a > b;
}
```

과 같이 만들어 주면 된다.



이를 응용한다면

```c++
bool compare(pair<int, int> a, pair<int, int> b){
	return a.second > b.second;
}
```

과 같이 응용할 수도 있다.
