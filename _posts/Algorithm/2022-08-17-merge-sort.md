---
title: 합병 정렬(Merge Sort)
categories: 
  - Algorithm
excerpt: 합병 정렬에 대해서 공부해보자.
date: 2022-08-17
tags:
- sort
- merge sort
---



> # 합병 정렬(Merge Sort)
---

## 개념 요약

- ‘존 폰 노이만(John von Neumann)’이라는 사람이 제안한 방법
- 일반적인 방법으로 구현했을 때 이 정렬은 안정 정렬 에 속하며, 분할 정복 알고리즘의 하나 이다.
  - 분할 정복(divide and conquer) 방법
    - 문제를 작은 2개의 문제로 분리하고 각각을 해결한 다음, 결과를 모아서 원래의 문제를 해결하는 전략이다.
    - 분할 정복 방법은 대개 순환 호출을 이용하여 구현한다.
- 과정 설명
  1. 리스트의 길이가 0 또는 1이면 이미 정렬된 것으로 본다. 그렇지 않은 경우에는
  2. 정렬되지 않은 리스트를 절반으로 잘라 비슷한 크기의 두 부분 리스트로 나눈다.
  3. 각 부분 리스트를 재귀적으로 합병 정렬을 이용해 정렬한다.
  4. 두 부분 리스트를 다시 하나의 정렬된 리스트로 합병한다.
<br />

# 과정

- 하나의 리스트를 두 개의 균등한 크기로 분할하고 분할된 부분 리스트를 정렬한 다음, 두 개의 정렬된 부분 리스트를 합하여 전체가 정렬된 리스트가 되게 하는 방법이다.
- 합병 정렬은 다음의 단계들로 이루어진다.
  - 분할(Divide): 입력 배열을 같은 크기의 2개의 부분 배열로 분할한다.
  - 정복(Conquer): 부분 배열을 정렬한다. 부분 배열의 크기가 충분히 작지 않으면 순환 호출 을 이용하여 다시 분할 정복 방법을 적용한다.
  - 결합(Combine): 정렬된 부분 배열들을 하나의 배열에 합병한다.
- 합병 정렬의 과정
  - 추가적인 리스트가 필요하다.
  - 각 부분 배열을 정렬할 때도 합병 정렬을 순환적으로 호출하여 적용한다.
  - 합병 정렬에서 실제로 정렬이 이루어지는 시점은 2개의 리스트를 합병(merge)하는 단계 이다.
 ![image](https://user-images.githubusercontent.com/76837780/185044560-e76c40e4-1195-47f0-8e27-547215412cb7.png)



# 예제

- 배열에 27, 10, 12, 20, 25, 13, 15, 22이 저장되어 있다고 가정하고 자료를 오름차순으로 정렬해 보자.
- 2개의 정렬된 리스트를 합병(merge)하는 과정
  1. 2개의 리스트의 값들을 처음부터 하나씩 비교하여 두 개의 리스트의 값 중에서 더 작은 값을 새로운 리스트(sorted)로 옮긴다.
  2. 둘 중에서 하나가 끝날 때까지 이 과정을 되풀이한다.
  3. 만약 둘 중에서 하나의 리스트가 먼저 끝나게 되면 나머지 리스트의 값들을 전부 새로운 리스트(sorted)로 복사한다.
  4. 새로운 리스트(sorted)를 원래의 리스트(list)로 옮긴다.
 ![image](https://user-images.githubusercontent.com/76837780/185045014-7ed84588-ad90-4c56-b364-b7d91c2a56b6.png)


[참조](https://gmlwjd9405.github.io/2018/05/08/algorithm-merge-sort.html)

# 문제예시

- [백준 11728. 배열 합치기](https://www.acmicpc.net/problem/11728)

```c++
#include <iostream>
using namespace std;

int main() {
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
    int n, m;
    int a_index = 0, b_index = 0;

    cin >> n >> m;

    int a[1000001], b[1000001];

    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }
    for (int i = 0; i < m; i++) {
        cin >> b[i];
    }
    //merge_sort 합병정렬
    while (a_index < n && b_index < m) {
        if (a[a_index] <= b[b_index]) {
            cout << a[a_index++] << " ";
        }
        else {
            cout << b[b_index++] << " ";
        }
    }
    //두개의 배열중 한배열이 비었을때 나머지 한배열 출력
    while (a_index < n) {
        cout << a[a_index++] << " ";
    }
    while (b_index < m) {
        cout << b[b_index++] << " ";
    }
}
```
