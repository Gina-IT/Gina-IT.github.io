---
title: Insertion sort (삽입 정렬)
author: Gina Sim
layout: post
---


*Insertion sort 란?*  
======

=> 새로운 카드를 기존에 정렬된 카드 사이의 올바른 위치에 넣는 카드정렬 방법과 유사  

![Insertion sort principle](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/insertion_sort.jpg "Insertion sort principle")  


**< Method >**  

1. 정렬이 필요한 기준 index는 배열 두번째 위치부터 시작  
2. 비교 index은 기준 index의 왼쪽에 위치  
3. 비교 index의 오른쪽에서부터 왼쪽으로 비교해 나가며 자신의 위치에 삽입  
4. 매 순서마다 기준 index의 수가 들어갈 위치를 찾아 넣음  
5. '모든 배열 수 -1'만큼 반복하면 전체 카드가 정렬  
   (기준 index가 배열 두번째 위치에서 시작하기 때문)  

--------------------


Pseudocode
------

**< Insertion sort >**  
j☞ 기준 index  
	- 설명 편의를 위해 정렬이 필요한 index값을 기준 index라 칭하고 설명하겠음  
i ☞ 비교 index  
	- 설명 편의를 위해 이미 정렬이 된 배열의 index 값들을 비교 index라 칭하고 설명하겠음  
	(이미 정렬된 숫자들과 비교해가면서 자신의 위치를 찾아야하기 때문)  

![Insertion sort pseudocode](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/insertion_sort_pseudocode1.jpg "Insertion sort pseudocode")  

--------------------

Code
------


**< main 함수 > - 배열 설정 및 출력**  
![Insertion sort_main code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/insertion_sort_main.jpg "Insertion sort_main code")  

**< Insertion sort 함수 >**  
![Insertion sort code](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/insertion_sort_code.jpg "Insertion sort code")  

**※ while 문**  

- ' i > -1' :-1보다 크다는 → 0부터 시작한다 → C 언어에서 배열의 index는 0에서 부터 시작
	=>비교 index 'i'가 배열을 벗어나지 않도록 하는 조건    
- ' A[i] > key' :key 값은 A[j]로 기준 index에 존재하는 배열의 값, 위의 예에서 key값은 검은색 칸  
	=>비교 index 'i'의 값이 key보다 크면 while문 수행  
- ' A[i+1]= A[i]', 'i= i-1'
	: 비교 index들의 값이 key값보다 작을 동안 i+1의 배열 값( A[i+1] ) 에 i의 배열값( A[i] ) 삽입    
	→ 비교 index 'i'를 'i -1' 시켜 오른쪽에서 왼쪽으로 이동하며 key 와 비교  
	→ key값보다 크면 A[i]을 A[i+1]에 삽입하며 값을 오른쪽으로 한칸씩 이동시킴  
	→ 마지막에 i가 -1의 위치로 벗어나면 while문 종료  
- ' A[i + 1]= key': 위 예에서 while문 벗어난 후 'i 위치'는 -1 → 'i+1'의 위치는 0(배열 첫째 자리)  
	=>배열의 첫째 자리에 key값 삽입  

--------------------

Result
------
 
![Insertion sort result](https://github.com/Gina-IT/Gina-IT.github.io/blob/master/_img/insertion_sort_result.jpg "Insertion sort result")
