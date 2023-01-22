# 섹션2: C언어 기본 문법 1
## 19. C언어의 기본 문법
<hr>

C언어는 옛날에 맞는 방식의 자료형이 존재하고,<br>
어떤 자료형은 n byte라고 표준에 정의되지 않은 부분이 있다.

<hr>

## C89에서 사용하는 기본 자료형
1. char
2. short
3. int
4. long
5. float
6. double
7. long double

<hr>

## signed / unsigned
부호 없는 자료형 앞에 **unsigned** 라는 단어를 앞에 붙여야 함<br>
앞에 달리 표현이 없으면 부호가 있는 **signed**인 것이 일반적<br>
**이지만** <br>
예외인 **char**가 있다.<br>
> 데이터를 표현하는 가장 작은 단위는 예외적이다.
> 
**char은 일반적으로 1 byte짜리 정수임**<br>