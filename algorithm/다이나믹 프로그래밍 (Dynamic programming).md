> ### 동적 계획법(dynamic programming)이란?

 복잡한 문제를 간단한 여러 개의 문제로 나누어 푸는 방법을 말한다. <br>다시 말하면 작은 부분문제들의 답을 구하여 _**저장**_하고 그 답을 _**참조**_하여 더 큰 문제들의 답을 구하는 방법이다. <br>작은 문제들의 답을 _**반복계산하지 않는다**_ !! 작은 문제들의 답을 _**참조**_만 !! 

 작은 부분문제들의 답을 **저장**하기 위하여 1-3차원 배열을 이용한다. 

> ### 1차원 배열을 이용해 푸는 DP문제

[가장 긴 증가하는 부분 수열 문제](https://www.acmicpc.net/problem/11053)

풀이 
```
#include <iostream>
using namespace std;

int n;
int mx;
int li[1001];
int dy[1001] = {0,};

int main(){
	//freopen("input.txt","r",stdin);
	ios_base :: sync_with_stdio(false); cin.tie(NULL); cout.tie(NULL);
	
	cin >> n;

    for(int i=1; i<=n; i++){
        cin >> li[i];
    }

    li[0] = 0;
    for(int i=1; i<=n; i++){
        for(int j=0; j<i; j++){
            if(li[i] > li[j] && dy[i] <= dy[j]){  
				dy[i] = dy[j] +1;
            }
        }
    }

    mx = 0;
    for(int i=1; i<=n; i++){
        if(dy[i] > mx){
            mx = dy[i];
        }
    }

    cout << mx;

}
```

> ### 2차원 배열을 이용해 푸는 DP문제

[평범한 배낭 문제](https://www.acmicpc.net/problem/12865)

```
#include <iostream>
using namespace std;

int n, k;
int w[101];
int v[101];
int dy[101][100001] = {0,};

int main(){
	//freopen("input.txt", "r", stdin);
	ios_base::sync_with_stdio(false); cin.tie(NULL); cout.tie(NULL);

	cin >> n >> k;

	for(int i=1; i<=n; i++){
		cin >> w[i];
		cin >> v[i];
	}

	for(int i=1; i<=n; i++){
		for(int j=w[i]; j<=k; j++){
			if(dy[i-1][j] < v[i] + dy[i-1][j-w[i]]){
				dy[i][j] = v[i] + dy[i-1][j-w[i]];
			}
			else{
				dy[i][j] = dy[i-1][j];
			}
		}
		for(int j=1; j<w[i]; j++){
			dy[i][j]=dy[i-1][j];
		}
	}

	cout << dy[n][k];

}
```





