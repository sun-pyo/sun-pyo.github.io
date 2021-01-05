---
layout: post
title: Programmers 49993 스킬트리
noindex: true
---

![로고 이미지](https://s3.ap-northeast-2.amazonaws.com/grepp-cloudfront/programmers_imgs/design/logo.jpg)

#### 문제 링크 : [https://programmers.co.kr/learn/courses/30/lessons/49993](https://programmers.co.kr/learn/courses/30/lessons/49993){: target="_blank"}


## 나의 풀이
모든 문자열에 대해 각각의 문자가 선행스킬이 있는 문자에 포함되면 선행 스킬의 순서가 맞는지를 확인하였다.




## 풀이 코드 : [49993 스킬트리 ](https://github.com/sun-pyo/algorithm/blob/main/programmers/skilltree.cpp){: target="_blank"}

```c++
#include <string>
#include <vector>
#include <queue>

using namespace std;

int solution(string skill, vector<string> skill_trees) {
    int answer = 0;
    vector<int> check;
    for(int i = 0;i<skill.size();i++){   
        check.push_back(skill[i]- 'A');
    }
    
    for(int i = 0;i<skill_trees.size();i++){
        int idx = 0;
        bool fail = false;
        
        for(int j = 0;j<skill_trees[i].size();j++){
            for(int c = 0;c<check.size();c++){
                if(skill_trees[i][j] - 'A' == check[c]){
                    if(c != idx){
                        fail = true;
                        break;
                    }
                    idx++;
                    break;
                }    
            }
            if(fail) break;
        }
        if(fail) continue;
        answer++;
    }
    return answer;
}
```





## 채점결과

![49993](\algorithm\img\49993.PNG)