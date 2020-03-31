---
layout: post
title: Programmers - 2
comments: true
categories : [Algorithm/Programmers]
tags: [Algorithm, Programmers]
---

<br><br>

# Programmers - 2

## 문제 설명

배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하려 합니다. <br>
예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면 <br>

- array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다.
- 1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다.
- 2에서 나온 배열의 3번째 숫자는 5입니다.

## 제한사항

- array의 길이는 1 이상 100 이하입니다.
- array의 각 원소는 1 이상 100 이하입니다.
- commands의 길이는 1 이상 50 이하입니다.
- commands의 각 원소는 길이가 3입니다.

```javascript
function solution(array, commands) {
    var answer = [];
    commands.forEach( c => {
        var arr = new Array(c[1] -  c[0] + 1); 
       for(var i = 0; i < arr.length; i++){
           arr[i] = array[c[0] - 1 + i];
       } 
        arr.sort((a, b) => {
            return a - b;
        });
       answer.push(arr[c[2]-1]);
    });
    return answer;
}
```