# [C++]lower_bound, upper_bound

 lower_bound, upper_bound



###### - 기본적으로 두개 모두 "이진 탐색(Binary Serch)" 기반의 탐색방법



# lower_bound

```c++
lower_bound(arr, arr + n, key);
```



#####  - key 값의 가장 낮은 위치를 찾는다.

#####  - key 값이 없다면 key 값보다 큰 가장 작은 정수의 위치를 반환한다.

#####  - 반환값이 "iterator" 이다.





# upper_bound

```c++
upper_bound(arr, arr + n, key);
```



#####  - key 값을 초과하는 가장 첫번째 원소의 위치.

#####  - 반환값이 "iterator" 이다.
