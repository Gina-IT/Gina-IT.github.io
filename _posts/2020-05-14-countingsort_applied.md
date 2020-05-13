---
title: Counting sort 응용 문제
author: Gina Sim
layout: post
category: Cprogramming  
---

문제  
------  
*n개의 영문 대소문자로만 구성된 배열 A[0..n-1]를 counting sorting하여 배열 B[0..n-1]를 생성하는 char_counting_sort 함수를 구현하시오. 이 때 return 값은 A[0] 원소가 놓여지는 배열 B에서의 index 값 k이다. (0≤ k ≤ n−1).*  

**제약 조건**  
- 함수의 prototype은 다음과 같다.    
	int char_counting_sort(char A[], char B[], int n);  
	A : 입력 배열  
	B : 정렬된 결과 배열  
	n : 배열의 크기   
	반환값 : A[0] 원소가 놓이게 되는 배열 B에서의 index값   
- 영문 대소문자의 크기 순서는 다음과 같다.A < a < B < b < C < c ...< Z < z  

----------

## Pseudocode  

**< Counting sort >**  
<img src="/_img/counting_sort_pseudocode.JPG" alt="Counting sort pseudocode">  

----------

## Code  

**< main 함수 >**  
```c
#include <stdio.h>

int char_counting_sort(char A[], char B[], int n);

int main(int argc, char* argv[]) {
    int n = 10;
    char A[10] = { 'c','b','c','d','E','C','a','A','b','C' };
    char B[10];

    for (int i = 0; i < n; i++) printf("%c ", A[i]);
    printf("\n");

    int res = char_counting_sort(A, B, n);

    for (int i = 0; i < n; i++) 
    	printf("%c ", B[i]);   // 문자로 출력 (ASCII코드로 읽힘)
    printf("\n");

    printf("res= %d\n", res);
}
```  
  
**< char_counting_sort 함수 >**  
```c
void alphabet_to_num(char A[], int n);
void num_to_alphabet(char B[], int n);
int char_counting_sort(char A[], char B[], int n) {
    int i, j;
    char C[52];

    alphabet_to_num(A, n);

    //C 배열 원소값 전체 초기화
    for (i = 0; i <= 51; i++) C[i] = 0;

    //A배열 원소 값에 해당하는 C index의 원소값 하나씩 증가
    for (j = 0; j <= n - 1; j++)
        C[A[j]] = C[A[j]] + 1;

    //누적합산을 통해 해당 원소의 자리값 구함
    for (i = 1; i <= 51; i++)
        C[i] = C[i] + C[i - 1];

    //B배열에 C의 index값 넣음
    for (j = n - 1; j >= 0; j--) {
        B[C[A[j]] - 1] = A[j];
        C[A[j]] = C[A[j]] - 1;
    }

    int k = C[A[0]];

    num_to_alphabet(B, n);

    return k;
}

void alphabet_to_num(char A[], int n) {   // 정렬하기 위해 문자를 숫자 값으로 저장해줌
    int i;

    for (i = 0; i <= n - 1; i++) {
        if (65 <= A[i] && A[i] <= 90) {     // ASCII 코드 이용 '알파벳 대문자이면'
            A[i] = 2 * (A[i] - 65);     // A부터 Z까지 짝수값으로 설정 (0 ~ 50)
        }
        else if (97 <= A[i] && A[i] <= 122) {     // 알파벳 소문자이면
            A[i] = 2 * (A[i] - 97) + 1;     // a부터 z까지 홀수값으로 설정 (1 ~ 51)
        }
    }
}

void num_to_alphabet(char B[], int n) {   //출력하기 위해 다시 숫자를 문자로 변경
    int i;

    for (i = 0; i <= n - 1; i++) {
        if (B[i] % 2 == 0) {     // 짝수이면
            B[i] = (B[i] / 2) + 65;     //알파벳 대문자로 만들어줌 
        }
        else
            B[i] = ((B[i] - 1) / 2) + 97;     //알파벳 소문자로 만들어줌
    }
}
```

------------

## Result  

<img src= "/_img/counting_sort_result.JPG" alt="Character counting sort result">