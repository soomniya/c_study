# 섹션2: C언어 기본 문법 1
## 16. printf() 함수
<hr>

## printf() 함수
**서식에 맞게** 화면에  데이터를 출력할 때 사용하는 함수<br>
print **formatted**
<br>
WriteLine같은 함수가 없어서 \n 이스케이프 문자 넣어줘야 함<br>

<hr>

### printf() 함수로 **문자열** 출력하기

string.Format()이나 문자열 보간(`${}`) 대신 <br>
**서식 문자(format specifier) %s**를 사용하여야 함

name에 있는 값을 **%s(문자열 string)** 위치에 출력

```c#
// C#
string name = "soomniya";
Console.WriteLine("Hello, " + name);
// string.Format()
Console.WriteLine("Hello, {0}", name);
// 문자열string 보간
Console.WriteLine($"Hello, {name}");
```
> Hello, soomniya<br>

```c
/* C */
const char* name = "soomniya";
printf("Hello, %s\n", name);
```
> Hello, soomniya

<hr>

### printf() 함수로 **정수** 출력하기
string.Format()이나 문자열 보간(`${}`) 대신 <br>
**서식 문자(format specifier) %d**를 사용하여야 함

**%d(정수 decimal)** 에 입력한 순서 맞게 변수를 대입하고 **문자열**로 변환하여 출력

```c#
// C#
int num1 = 10;
int num2 = 90;
Console.WriteLine(num1 + num2);
// string.Format()
Console.WriteLine("{0} + {1}", num1, num2);
// 문자열string 보간
Console.WriteLine($"{num1} + {num2}");
```
> 10 + 90<br>

```c
/* C */
int num1 = 10;
int num2 = 10;
printf("%d + %d\n", num1, num2);
```
> 10 + 90

C는 **메모리 관리**를 직접 해주지 않음, 그래서 단순하게 해야 함

<hr>

## printf() 함수로 둘 다 같이 출력하기
**%d(정수 decimal)** 와 **%s(문자열 string)** 을 함께 사용하여 값이 들어갈 위치를 지정해줌

```c#
// C#
string name = "soomniya";
int day = 1;
Console.WriteLine("Hello, " + name + "!\n(Day " + day + ")");
// string.Format()
Console.WriteLine("Hello, {0}!\n(Day {1})", name, day);
// 문자열string 보간
Console.WriteLine($"Hello, {name}!\n(Day {day})");
```
> Hello, soomniya!<br>
> (Day 1)

```c
/* C */
string name = "soomniya";
int day = 1;
printf("Hello %s!\n(Day %d)\n", name, day);
```
> Hello, soomniya!<br>
> (Day 1)