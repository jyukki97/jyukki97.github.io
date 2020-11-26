# [C++]set predicate

 set predicate



`set` 이라는 컨테이너는 기본적으로 "오름차순" 으로 정렬된다.



이를 바꾸기 위해 정렬 기준을 바꿔 주어야한다.



정렬기준은

```c++
bool compare(const key_type key_typeA, const key_type key_typeB){

	return key_typeA < key_typeB;

}
```

와 같이 bool 형식을 통해 바꿀 수 있다.



정렬기준을 적용하는 방법은



```c++
set<key_type, decltype(&compare)> a(&compare)
```

과 같이 하면된다.
