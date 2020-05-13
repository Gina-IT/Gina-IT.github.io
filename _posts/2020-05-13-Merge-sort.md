---
title: Merge sort (합병 정렬)
author: Chris
layout: post
---

*Merge Sort 란?*  
======
 
=> Divide and Conquer방법 중 하나
- 배열을 2개의 조각으로 나눈 후 각각을 정렬하고 그 조각들을 다시 모아 원래 배열을 정렬시키는 방법
- 대개 순환 호출을 이용하여 구현
![Merge sort principle](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort.png "Merge sort principle")

**< Step >**  

**Step 1** Divide  
→ 입력 배열을 비슷한 크기의 2개의 부분 배열로 분할한다  
(ex. 배열 8개 -> 4개 4개 / 배열 9개-> 5개 4개)  

**Step 2** Conquer  
→ 부분 배열을 정렬한다.   

**Step 3** Combine  
→ 정렬된 부분 배열들을 하나의 배열로 합병  

※ 순환 호출을 통해 부분 배열의 크기가 충분히 작아지도록 계속해서 쪼개고, 정렬하고, 합병하는 방법을 반복하여 원래 배열이 모두 정렬되도록 함  
※ 배열의 길이가 0 또는 1이면 이미 정렬된 것으로 판단  

--------------------

Pseudocode  
------

**<Divide and Conquer>**  
![Merge sort pseudocode_merge](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort_pseudocode1.jpg "Merge sort pseudocode- merge")  

**<Combine>- Recurrunce**  
![Merge sort pseudocode_recurrunce](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort_pseudocode2.jpg "Merge sort pseudocode- merge sort")  

-------------------

Code  
------

**< main 함수 > - 배열 설정 및 출력**  
![Merge sort_ main code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort_main.jpg "Merge sort- main code")  


**< merge 함수> - Divide and Conquer**  
![Merge sort_ merge code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort_merge.jpg "Merge sort- merge code")   

**< merge sort 함수 > - Combine/ Recurrunce**  
![Merge sort_ merge sort code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort_mergesort.jpg "Merge sort- merge sort code")  

- 함수 내에서 함수를 호출함으로써 재귀적으로 합병 정렬을 하게 됨
: 함수 내에서 함수 호출 (순환 호출) → 배열이 반복적으로 쪼개지면서 계속 작은 단위로 분할 → 작은 단위에서 정렬 → 정렬된 작은 조각들이 합병 → 최종적으로 원래 배열 하나가 전체 정렬이 됨

-------------------

Result
------

![Merge sort result](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/merge_sort_result.jpg "Merge sort result")