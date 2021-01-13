---
layout: post
title: Beakjoon 1138 한 줄로 서기
noindex: false
---

![Baekjoon Online Judge](https://onlinejudgeimages.s3-ap-northeast-1.amazonaws.com/images/boj-og-1200.png)

#### 문제 링크 : [https://www.acmicpc.net/problem/1138](https://www.acmicpc.net/problem/1138){: target="_blank"}


## 나의 풀이
키가 작은 사람부터 자리를 결정한다.




## 풀이 코드 : [1138 한 줄로 서기 ](https://github.com/sun-pyo/algorithm/blob/main/Beakjoon/1138%ED%95%9C%EC%A4%84%EB%A1%9C%EC%84%9C%EA%B8%B0.cpp){: target="_blank"}

```c++
#include <stdio.h>
#include <vector>

using namespace std;

int arr[10];

int main(){
    int N, num;
    scanf("%d",&N);
    vector<int> input;
    
    for(int i =0;i<N;i++){
        scanf("%d",&num);
        input.push_back(num);
    }

    for(int i = 0;i<N;i++){
        int count = 0;
        for(int j=0;j<N;j++){
            if(count == input[i] && arr[j] == 0){
                arr[j] = i+1;
                break;
            }
            if(arr[j] == 0) count++;
        }
    }

    for(int i = 0;i<N;i++)
        printf("%d ",arr[i]);

}
```





## 채점결과

![49993](\algorithm\img\beakjoon_1138.PNG)