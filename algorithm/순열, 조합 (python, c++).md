> ### 순열 (permutation)

#### n개중에 r개를 _중복없이_ 뽑아  _순서있게_ 나열한 것
#### *_python 코드* <br>permutations(반복 가능한 객체, r)
```
from itertools import permutations
for i in permutations([1,2,3,4], 2):
	print(i, end=" ")
```
#### (1,2), (1,3), (1,4), (2,1), (2,3), (2,4), (3,1), (3,2), (3,4),(4,1), (4,2), (4,3) 
#### *_C++ 코드*
```
void rec(int x){
	if(x>r){
		return;
	}
	if(x==r){
		for(int i=0; i<r; i++){
			cout << nn[i] << " ";
		}
		cout << "\n";
		return;
	}
	for(int i=0; i<n; i++){
		if(check[i]==0){
			check[i] = 1;
			nn[x] = per[i];
			rec(x+1);
			check[i] = 0;
		}
	}
}
```

> ### 중복 순열 (product)

#### n개중에 r개를 _중복있게_ 뽑아  _순서있게_ 나열한 것
#### *_python 코드* <br>product(반복 가능한 객체, repeat=1)
```
from itertools import product
for i in permutations([1,2,3], repeat=2):
	print(i, end=" ")
```
#### (1,1), (1,2), (1,3), (2,1), (2,2), (2,3), (3,1), (3,2), (3,3)
#### *_C++ 코드*
```
void rec(int x){
	if(x>r){
		return;
	}
	if(x==r){
		for(int i=0; i<r; i++){
			cout << nn[i] << " ";
		}
		cout << "\n";
		return;
	}
	for(int i=0; i<n; i++){
		nn[x] = per[i];
		rec(x+1);
	}
}
```



> ### 조합 (combinations)

#### n개중에 r개를 _중복없이_ 뽑은 것 (순서X)
#### *_python 코드* <br>combinations(반복 가능한 객체, r)
```
from itertools import combinations
for i in combinations([1,2,3,4], 2):
	print(i, end=" ")
```
#### (1,2), (1,3), (1,4), (2,3), (2,4), (3,4)
#### *_C++ 코드*
```
void rec(int x, int xx){
	if(x>r){
		return;
	}
	if(x==r){
		for(int i=0; i<r; i++){
			cout << nn[i] << " ";
		}
		cout << "\n";
		return;
	}
	for(int i=xx; i<n; i++){
		if(check[i]==0){
			check[i]=1;
			nn[x]=com[i];
			rec(x+1,i+1);
			check[i]=0;
		}
	}
}
```

> ### 중복조합 (combinations_with_repeat)

#### n개중에 r개를 _중복있게_ 뽑은 것 (순서X)
#### *_python 코드* <br>combinations_with_repeat(반복 가능한 객체, r)
```
from itertools import combinations
for i in combinations([1,2,3], 2):
	print(i, end=" ")
```
#### (1,1), (1,2), (1,3), (2,2), (2,3), (3,3)
#### *_C++ 코드*
```
void rec(int x, int xx){
	if(x>r){
		return;
	}
	if(x==r){
		for(int i=0; i<r; i++){
			cout << nn[i] << " ";
		}
		cout << "\n";
		return;
	}
	for(int i=xx; i<n; i++){
		nn[x]=com[i];
		rec(x+1,i+1);
	}
}

