# 섹션2: C언어 기본 문법 1
## 26. 열거형
<hr>

- [ ] 다른 언어에서의 enum
  
C#과 다르게 명시적 캐스팅 없어도 _**int와 섞어서 사용 가능 👀💦**_
<br>


C에서의 열거형은 그냥 정수에 별명을 붙이는 수준임 (?)


```c#
// type 고정
enum day { MONDAY, TUESDAY };
enum month { JAN, FEB };

day hump_day = day.MONDAY;
/* 컴파일 오류 */
month birth_month = hump_day;

```

```c
enum day { MON, TUES };
enum month { JAN, FEB };

enum day hump_day = MON;
/*
    컴파일이 된다!
    태어난 달이 화요일이 됨
*/
enum month birth_month = hump_day;
```

따라서 위와 같은 실수를 방지하고자, 코딩 표준으로 enum 이름을 앞에 표기하도록 정함.

```c
enum day { DAY_MON, DAY_TUES };
enum month { MONTH_JAN, MONTH_FEB };
```