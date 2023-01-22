# 섹션2: C언어 기본 문법 1
## 20. char형
<hr>

> 표준: **최소** 8 bit인 정수형

<br>
최소 8 bit라는 것은... 꼭 그 크기가 1 byte라는 뜻은 아니다...<br>
최소 8 bit 이기 때문에 그보다 더 큰 크기로 설정해도 표준에는 어긋나지 않음 ^_^

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

```c
char ch_a = 'a';
char ch_b = ch_a + 1; /* == 'b' */
char ch_c = 99; /* == 'c' */
```
