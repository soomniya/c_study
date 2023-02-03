# 섹션2: C언어 기본 문법 1
## 23. float형
<hr>

> 표준: IEEE 754가 아닐 수도 있음! **char 이상** <br>
> unsigned 없음


C 표준 👀💦
<br>

### (일반적인 플랫폼에 맞추어 개발한다고 할 때)float
* 크기: **32 bit**
* 범위: IEEE 754 Single과 동일
* 관련 헤더 파일: float.h

<hr>

## float의 **literal**
f(또는 F): **float**를 표현하는 접미사 //거의 소문자 f 사용
<br>

```c

float pi1 = 3.14f;

/*
    컴파일 오류
    float은 unsigned가 없다!
*/
float pi1 = 3.14uf;
```

<hr>

## 23. double형
<hr>

> 표준: IEEE 754가 아닐 수도 있음! **float 이상** <br>
> unsigned 없음

C 표준 👀💦

<br>

#### 일반적인 표준에서의 double
CPU가 계산에 사용하는 기본 데이터 크기

<br>

### (일반적인 플랫폼에 맞추어 개발한다고 할 때)double
* 크기: **64 bit**
* 범위: IEEE 754 Double과 동일
* 관련 헤더 파일: float.h

<hr>

## double의 **literal**
없다!

<br>

```c
/* 컴파일 */
double num = 3.14;

/* 컴파일 오류 */
unsigned double unsigned_num = 3.14;

/* 컴파일 오류 */
signed double signed_num = -3.14;
```

<hr>

## 23. long double형
<hr>

> 표준: **double 이상** <br>
> unsigned 없음 <br>
> double보다 **정밀도가 높다** <br>
> double보다 bit를 많이 사용하는 data를 위함

<br>

다른 언어에는 별로 없는 data type👀💦

#### 일반적인 타언어에서의 double
C의 long double과 유사한 느낌

<br>

### (일반적인 플랫폼에 맞추어 개발한다고 할 때)double
* 크기: **64 bit**
* 범위: IEEE 754 Double과 동일
* 관련 헤더 파일: float.h

<br>

```c
/* 컴파일 */
long double num = 3.14;

/* 컴파일 오류 */
unsigned long double unsigned_num = 3.14;

/* 컴파일 오류 */
signed long double signed_num = -3.14;
```

<hr>

## 23. 결론
<hr>

데스크탑에서는 다른 언어와 비슷하게 사용 가능하다
* 예외: long (32 bit 임)

소형 기기 다룰 때는 매뉴얼에서 자료형 크기 확인할 것
* 범용성 있게 코드를 작성하려면: 포팅이 보장되는 범위의 값을 사용

float, double은 플랫폼 사이에 값이 불일치 할 수도 있음