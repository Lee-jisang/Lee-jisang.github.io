---
title: 이분(이진)탐색(Binary Search)
categories: 
  - Algorithm
excerpt: 이분(이진)탐색에 대해서 공부해보자.
date: 2022-05-25
tags:
- binary search
---



> # 이분탐색(Binary Search)
---

## 개념

- 이진 탐색 알고리즘(Binary Search Algorithm)은 오름차순으로 정렬된 리스트에서 특정한 값의 위치를 찾는 알고리즘 입니다.
- 오름차순으로 정렬된 리스트의 중간 값을 임의의 값으로 선택하여, 찾고자 하는 Key값과 비교하는 방식으로 돌아가는 알고리즘 입니다.
- **정렬된 리스트**에서만 사용할 수 있다는 단점이 존재합니다.
- 검색이 될때마다 선형탐색(Linear Search)와는 비교할 수 없게 빨라집니다.
<br />


## 코드 구현

```c++
#include <iostream>
using namespace std;

int main()
{
   // 1~500까지의 배열 형성
   int arr[501];
   for(int i=1;i<501;i++)
      arr[i]=i;

   int target = 62; // 타겟 값
   // 이분 탐색 수행
   int left = 1, right = 500; // left, right 초기화
   while(left<=right)
   {
      int mid = (left+right)/2 // mid 갱신
      // 타겟 값 찾음
      if(mid==target)
      {
         cout<<"Searching Complete!"<<'\n';
         break;
      }
      else if(mid>target)
      {
         right = mid-1;
      }
      else
      {
         left = mid+1;
      }
   }
   return 0;
}
```

[수 찾기](https://www.acmicpc.net/problem/1920)

```c++
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
	ios::sync_with_stdio(false);
	cin.tie(NULL);

	int n, m, num;
	cin >> n;
	vector<int> v(n);

	for (int i = 0; i < n; i++) {
		cin >> v[i];
	}
	sort(v.begin(), v.end());

	cin >> m;
	for (int i = 0; i < m; i++) {
		cin >> num;
		if (binary_search(v.begin(), v.end(), num)) { //이분탐색해서 타깃을 찾으면
			cout << "1" << "\n";
		}
		else cout << "0" << "\n";
	}
	return 0;
}
```
