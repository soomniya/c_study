# 섹션2: C언어 기본 문법 1
## 20. char형
<hr>

> 표준: **최소** 8 bit인 정수형

<br>
최소 8 bit라는 것은... 꼭 그 크기가 1 byte라는 뜻은 아니다...<br>
최소 8 bit 이기 때문에 그보다 더 큰 크기로 설정해도 표준에는 어긋나지 않음 ^_^
<br>
일반적으로 1 byte는 8 bit이지만, C에서는 꼭 그렇지도 **않다**.
<br>
C에서는 `CHAR_BIT`의 값에 따라 1 byte의 값이 **달라진다**.
<br>

> C는 기기에서 자주 쓰였기 때문에, 이 부분은 HW 설계자의 마음이라...

```c
#include <limits.h>
int main(void)
{
    char char_size = CHAR_BIT;
    return 0;
}
```
>8'\b'

<hr>

## char와 ASCII 문자

```c
char ch_a = 'a';
char ch_b = ch_a + 1; /* == 'b' */
char ch_c = 99; /* == 'c' */
```

### ASCII 문자
* 정수형
* 아스키 문자는 0~127
  *  2^7이기 때문에 char로 표현하기 충분하다.
  *  부호 1 bit + 7 bit
  *  기본적으로 아스키 코드를 쓸 때는 부호 bit는 사용 X

## char와 signed/unsigned
char는 정수형이기 때문에, signed와 unsigned로 나뉠 수 있음
<br>
_보통의 정수형은_ 부호가 생략되면 **signed**이지만
<br>
C 표준으로 정해지지 않았기 때문에
<br>
_**컴파일러에 따라 달라진다.**_
<br>
> clang에서의 char: **signed**

<br>

따라서, 숫자를 표현하기 위한 char는 signed/unsigned를 **명시적**으로 나타내야 한다.

<br>
명시적으로 하지 않았을 경우,
<br>
값이 0~127(최상위 부호 bit를 뺀 7 bit만 사용)인 경우에만 어떠한 플랫폼에서도 문제 없이 작동한다.
<br>

- [ ] 포팅


<br>

**💡 컴파일 중에 char의 부호를 알 수 있는 방법**
<br>
하지만 처음 선언할 때 부호를 명시했다면, 굳이 이런 식으로 확인할 필요도 없다!
### <limits.h>
```c
/* signed일 경우 */
#define SCHAR_MIN (-128)

/* unsigned일 경우 */
#define SCHAR_MIN (0)

#ifndef _SCHAR_UNSIGNED
    #define CHAR_MIN        SCHAR_MIN
    #define CHAR_MAX        SCHAR_MAX
#else
    #define CHAR_MIN        0
    #define CHAR_MAX        UCHAR_MAX
#endinf
```
### char로 표현 가능한 숫자의 범위
**포팅 문제 없는 범위**
<br>

| unsigned char | char | signed char |
| :--: | :--: | :--: |
| 0 ~ 255 | 0 ~ 127 | -127 ~ 127 |
<br>

**💡 signed 범위가 왜 -127부터일까?**
<br>
_1의 보수_...를 사용하는 기계에 포팅하기 위해 안전하게 설정한 범위
<br>
0이 두 개이다. **➕0, ➖0**
<br>

### (일반적인 플랫폼에 맞추어 개발한다고 할 때)char로 표현 가능한 숫자의 범위
* 크기: 8 bit
* 부호를 생략하면: signed (명확하진 않지만)
* 범위:
  * signed: -128 ~ 127 (1의 부호 사용 X)
  * unsigned: 0 ~ 255
