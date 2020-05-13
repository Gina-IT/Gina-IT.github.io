---
title: 숫자와 문자 분리하기
author: Gina Sim
layout: post
category: Cprogramming
---

문제
------

*"숫자와 문자가 섞여있는 문자열을 입력받고, 숫자와 문자를 분리하여 추출하기"*

-----------

### Code  

```c
#include <stdio.h>
#include <string.h>

int main()
{
	char s[50];     // 입력받은 문자열 저장 

	printf("숫자가 섞인 문장을 입력하세요: ");
	scanf("%s", s);
	printf("\n");

	int num[50];     // 숫자를 저장할 배열 
	int nidx = 0;      

	char str[50] = " ";     // 문자를 저장할 배열 
	int sidx = 0;

	int len = strlen(s);   //문자열 s의 길이를 len 변수 값으로 지정
	int i;
	
	for ( i = 0; i < len; i++)
	{
		if ('0' <= s[i] && s[i] <= '9')   // s를 char로 선언하였기 때문에  ASCII코드 이용하여 "'0~9'인 경우"의 조건을 준 것 
		{
			num[nidx] = s[i] - '0';    
			nidx++;  
		}
		else
		{
			str[sidx]=s[i];
			sidx++;
		}
	}

	printf("%s\n", str);
	for ( i = 0; i < nidx; i++)
	{
		printf("%d", num[i]);
	}
}
```  
- num[nidx] = s[i] - '0';     
	: 출력할 때 %s가 아닌 %d로 출력하기 위해 ASCII코드 값 '0'을 빼준다   
	 예) 2= ASCII코드 50, 0= ASCII코드 48  -> 숫자 2에 대해 ('2' - '0'= 50-48= 2)  
	 => %d로 출력할 때 2가 출력 됨  

----------

### Result  

  
<img src= "/_img/extractnum_result.JPG" alt="Extract number from characters_result">
