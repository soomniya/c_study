# 섹션2: C언어 기본 문법 1
## 14. #include, stdio.h
<hr>

## #include
* 다른 파일에 구현된 함수or변수를 사용할 수 있게 해 줌
* 전처리기(preprocessor)
  * 컴파일 전 소스코드를 복붙해줌
  * // 추후 다시
<hr>

## <>
* 실제 디스크 상 존재하는 파일 이름을 <> 안에 기록
* #include<*.h> 안에 기록된 파일 이름을 찾아 포함시킴
* 헤더파일(*.h)을 열어 그 내용을 복사, 호출한 소스코드 내에 #include ~ 라인을 불러온 소스코드로 대체하여 컴파일
    ```C
    #include <stdio.h>
    /* 
    >> stdio.h 내 코드로 대체됨
    */

    ``` 

<hr>

## #include <stdio.h>
1. #inlcude <stdio.h>
   * 표준
2. #include 'stdio.h'
   * **컴파일 오류**

3. #include "stdio.h"
   * 컴파일은 되지만
   * [ ] stdio.h 한해 굳이 할 필요 없는(?) // 추후 다시

<hr>

### C 표준 라이브러리
* 매크로
  * 수학 계산
  * 입출력 처리
  * 메모리 관리
* 자료형(data type)
* 함수
등을 모아 놓은 것

<hr>

### <stdio.h>
* C 표준 라이브러리(C Standard Library, **libc**) 중 일부
* 표준 입출력(**St**an**d**ard **I**nput and **O**utput)을 담당
* 스트림 입출력에 관련된 함수들을 포함
  * printf()
  * scanf()
  * fopen()
  * fclose()