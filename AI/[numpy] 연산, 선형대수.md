### 왜 numpy를 사용해야 할까요 ? 

#### - list보다 numpy.array가 속도 훨씬 빠르기 때문 

### numpy.array
#### - numpy의 container, array
```
arr = np.array([1, 2, 3]) 
> array([1, 2, 3])
arr.shape  # 몇차원인지 
> (3,)

arr_2d = np.array([[1,2,3], [4,5,6], [7,8,9]])
> array([[1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]])
arr_2d.shape  # 몇차원인지 
> (3, 3)
```
> ### numpy의 연산

- ### vector와 scala 사이의 연산 
 #### - 벡터의 각 원소에 대해 연산을 수행
 
- ### vector와 vector사이의 연산
 #### - 벡터의 _같은 인덱스_끼리 진행
- ### array slicing 
 #### - python list와 유사하게 진행
 ```
 W = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])
 W[0:2, 1:3]
 > array([[2, 3],
       [6, 7]])
 ```
 
> ### numpy와 선형대수

 - ###  영벡터(행렬)
 #### - 모든 원소가 0 인 벡터
 #### - np.zeros(dim) dim은 값 또는 튜플

 - ### 일벡터(행렬)
 #### - 모든 원소가 1인 벡터
 #### - np.ones(dim) 

 - ### 대각행렬
 #### - np.diag((main_diagonals))
 
 - ### 항등행렬
 #### - np.eye(n, (dtype= int, float ...))

 - ### 행렬 곱
 #### - np.dot() or @

 - ### 트레이스
 #### - 대각성분의 합
 #### - np.trace()

 - ### 행렬식
 #### - np.linalg.det()

 - ### 역행렬
 #### - np.linalg.inv()

 - ### 고유값과 고유벡터
 #### - 정뱡행렬 A에 대해 $ Ax = λx $을 만족하는 λ와 x를 각 고유값과 고유벡터라 한다.
 #### - np.linalg.eig()




