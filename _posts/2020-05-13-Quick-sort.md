---
title: Quick sort (퀵 정렬)
author: Gina Sim
layout: post
category: Algorithms
---

*Quick Sort란?*  
======  

=> Divide and Conquer방법 중 하나  
	- 배열을 2개의 조각으로 나눈 후 각각을 정렬하고 그 조각들을 다시 모아 원래 배열을 정렬시키는 방법  
	- 대개 순환 호출을 이용하여 구현  

=> Merge Sort(합병정렬)과 달리 비균등한 크기로 나눔  
	- Pivot 값을 기준으로 값이 더 작은 원소들과 큰 원소들로 나눔  

![Quick Sort principle](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort.jpg "Quick sort principle")  


**< Step >**  

**Step 1** Pivot 값 설정  
→ 배열의 끝 값을 pivot 값으로 지정  

**Step 2** Divide  
	→ Pivot 값을 기준으로 값이 더 작은 원소와 큰 원소로 나눔  
	(ex. 위 사진에서 밑에서 두 번째 배열)  
	→ 마지막에 Pivot 값을 중간으로 보내 줌  
	(ex. 위 사진에서 마지막 배열 )  

**Step 3** Conquer  
	→ 부분 배열을 정렬한다 (순환 호출 이용)  

**Step 4** Combine  
	→ 정렬된 부분 배열들을 하나의 배열로 합병  

※ 순환 호출을 통해 부분 배열의 크기가 충분히 작아지도록 계속해서 쪼개고, 정렬하고, 합병하는 방법을 반복하여 원래 배열이 모두 정렬되도록 함  
※ 배열의 길이가 0 또는 1이면 이미 정렬된 것으로 판단  

----------

Pseudocode  
------

**< Quick Sort > - Recurrunce**  

![Quick sort pseudocode_ recurrunce](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort_pseudocode1.jpg "Quick sort pseudocode")  


**< Partitioning >**  

![Quick sort pseudocode_ partitioning](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort_pseudocode2.jpg "Quick sort pseudocode_partitionin")  

----------

Code   
------  
  
**< main 함수 > - 배열 설정 및 출력**    
![Quick sort_ main code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort_main.jpg "Quick sort- main code")

- 8개의 원소 값을 가지기 때문에 -> A[8]  
- C언어에서 index( i )값은 0부터 시작하기 때문에 index 범위는 0~7  
   -> quicksort(A, 0, 7)  
  
  
**< quick sort 함수 > - Recurrunce**  
![Quick sort_ quicksort code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort_recurrunce.jpg "Quick sort- quicksort code(recurrence)")  
   
**< partition 함수 > - Divide and Conquer**  
![Quick sort_ partition code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort_partition.jpg "Quick sort- partition code")  
  
- i : pivot 값을 기준으로 반으로 나눈 후 중간점을 구분하기 위한 index  
- j : pivot 값과 비교해나가는 원소의 index  
- swap 함수 : 정렬 과정에서 두 값의 위치를 편하게 바꿔주기 위해 함수로 만듦  
- swap(&A[ i+1 ], &A[ r ])  
   → A[i+1]와 A[r]을 바꿈으로써 pivot 값을 중간으로 이동  
   → index i 까지는 pivot보다 작은 값  
   → A[i+1]은 pivot 값  
   → A[ i+2]부터 끝까지는 pivot 보다 큰 값  

----------
Result  
------

![Quick sort result](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/quick_sort_result.jpg "Quick sort rusult")

