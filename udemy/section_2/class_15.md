# 섹션2: C언어 기본 문법 1
## 15. main(void) 함수
<hr>

## main(void) 함수
> 프로그램의 진입점(entry point)
```C
int main(void)
{
    return 0;
}
```

C코드를 빌드한 결과물을 실행하면 main(void) 함수가 자동적으로 실행됨<br>

int main(void): int형을 반환해야 함<br>


일반적으로는 **0**을 반환하면 프로그램에 문제가 없음을 의미<br>
**그 외 값**은 오류가 있음을 의미
<hr>

* [ ] C는 **절차적**이다

<hr>

## 빌드, 컴파일, 실행하기
```shell
clang -std=c89 -W -Wall -pedantic-errors main.c
```
* clang: c/c++/objective-c 컴파일러
* -std=c89:
c89 표준으로
* 컴파일 플래그
  * [-W](https://releases.llvm.org/6.0.0/tools/clang/docs/DiagnosticsReference.html#w)
  * [-Wall](https://releases.llvm.org/6.0.0/tools/clang/docs/DiagnosticsReference.html#wall)
  * [-pedantic-errors](https://clang.llvm.org/docs/UsersManual.html#cmdoption-pedantic-errors)
* main.c: 빌드할 파일
  * *.c: 모든 c파일 컴파일하여 실행 파일 빌드
  * 특별히 이름을 지정하지 않으면 'a'로 빌드됨
  * 리눅스 환경: a.out
  * 윈도우 환경: a.exe
  * [ ] 다른 이름으로 빌드하기: -o

<hr>

## 프로그램 종료 코드 확인하기

* 윈도우 cmd
  * errorlevel이라는 변수 출력
    ```cmd
    echo %errorlevel%
    ```
* shell
  * errorlevel이 아닌 ? 사용
    ```shell
    echo $?
    ```
<hr>

## main(void) 함수: (**void**)
C는 함수 선언과 함수 정의가 분리되어 있음.<br><br>
C언어는 다른 언어와 달리 함수 **선언**에서 void를 생략한다고 == int main();이라고  **매개변수가 없다는 뜻이 아님** <br>
함수 선언에서 void를 생략하면 **매개변수를 받는다**는 뜻 <br>
아직 어떤 type인지, 몇 개일지 모를 매개변수가 **있음**<br>
void를 명시적으로 선언하면, 정말 **매개변수가 없음**을 의미 <br><br>
함수 **정의**에서 void를 생략하면 **매개변수가 없음**을 의미<br>

```c
/* 함수 선언 */
/* 매개변수 없음 */
int sum(void);

/*
    매개변수 있음
    다만 매개변수가 몇 개인지 어떤 타입인지 아직 모름
*/
int sum();

/* 함수 정의 */ 
int sum(void)
{
    /*
        매개 변수 없음
    */
}

/* 함수 정의 */ 
int sum()
{
    /*
        매개 변수 없음 !!!
    */
}

/* 함수 정의 */ 
int sum(const int num1, const int num2)
{
    /*
        매개 변수 있음
    */
}
```
<hr>

## main() 함수와 커맨드 라인 인자
* [ ] 추후 포인터, C스타일 string 보고 나서 다시 보기
```c
/* 예시1 */
int main(int argc, char* argv[])
{
    return 0;
}

/* 예시2 */
int main(int argc, char** argv)
{
    return 0;
}
```