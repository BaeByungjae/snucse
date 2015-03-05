시스템 프로그래밍
========

> 3월 3일

* 컴구의 내용을 알아야 수업을 할수있음

### Introducing Computer Systems from a Programmer's Perspective

- Randal E. Bryant, David R. O'Hallaron
- Computer Science and Electrical Engineering
- Carnegie Mellon University

### Outline

Introduction to Computer Systems

* Course taught at CMU since Fall, 1998

학생들에게 무엇을 제일 먼저 가르쳐야 하는가? 어떤 언어를 가르치는것이 제일
좋은것인가? 지난 30년동안 제일 싸워가면서 굉장히 많이 바뀌어왔다. 지금은 좀
먼지가 가라앉은것같은데 여전히 ㄱ싸우긴함. 지금 두가지 진영이 있는데, 한 진영은
우리학교처럼 C를 먼저 가르치는 긴영, 한 진영은 카이스트처럼 파이썬을 먼저
가르치는 진영. 이건 중국집악서 짜장면 짬뽕가은 둘다 장단이 있고 정답은 없음.
가장 기본적인 프로그래밍이라는것을 배웠다고 치면, 헬로월드는 쓸수 있다고 치고,
이제 시간이 지나면 그 다음엔 컴퓨터 시스템이라는게 어떻게 생겼는지. 컴퓨터가
뭐하는거냐는 대부분 알고있는데, 컴퓨터 시스템이라는건 뭐냐. 이 속에 뭐가
들어있어서 이러한 일을 할 수 있게 하는건가. 컴퓨터 시스템이라는걸 어떻게
가르칠거냐.

제일 좋은 생각은 컴퓨터를 뜯어서 보여주는것. CPU는 이렇게 생겼다. 그래픽카드는
이렇게 새겼다. 각자가 하는일을 설명해주고. 더 나아가서는 뚜껑을 열어서
안에있는걸 보여주는게 더 나은데 CPU를 열어준다고 이게 뭐가 보이나? 확대경을
가져와서 보여줘동 ㅏ무것도 안보이는데.노트북 데스크탑은 눈에 보이는데 이속에서
무슨일이 일어나는지는 알수가 업다. 블랙박스 처럼. 이 속에서 무슨일이
일어나는지를 가르쳐보자 하는것이 바로 이 **책**이다. 단, 컴퓨터를 만드는 사람읭
ㅣㅂ장이 아니라 컴퓨터 프로그램을 프로그래킹 하는 프로그래머의 입장에서 짜는것.
내가 프로그래머가 아니고 뭐 한글가지고 웹서핑하고 이런일이나 하면 이게 필요가
없다. 하지만 프로그램을 만들어서 커다랑 시스템을 만든다 하면 바로 이걸
배워야된다 이거임.

### Computer Arithmetic

*Builder's Perspective*

컴퓨터를 만드는사람의 입장에서 봤을떄엔 얘네는 계싼을 하는 회로가 컴퓨터를
이루는 근간. 게이트를 만들어서 어떻게 신호가 빠르게 움직이게 하는지. 윗쪽에서
시그날이 오면 어떻게 아웃풋이 나가는지. 전자가 움직이는 속도는 정해져있으니
중간에 거쳐가는 게이트가 몇개가 있는지에 따라 시간이 결정되겠지? 게이트가 두개면
2, 게이트가 열개면 10, 이러한 서킷을 디자인하는사람들은 어떻게하면 이 DEpth를
어떻게 낮출수 있는지, 열개까지 거치지 않고 한두개만 통과하게 할지, 혹은 이
게이트 서킷 하나하나의 시간을 ㅈㄹ이는것이 목표. 내가 컴퓨터를 만드는사람이면
이것이 목표

*Programmer's Perspective*

프로그래머의 입장에선 이제 저 전자회로는 별 상관이 없다. 프로그래머 입자에선
그냥 프로그램을 짜ㅈㅆ을떄 결과가 나오고 잘 돌아가면 되는거야. 이 컴퓨터라는건
이런 프로그램을 만들어서 집어넣으면 돌아가면서 아웃풋이 나오는것이 컴퓨터가
이것이 바로 프로그래머가 알고잇는 전부죠.

(예제를 보여줌) 이렇게 이런 프로그램을 짰으면 엑스가
오부터 오십, 오백만까지 쭉 늘어나면서 제곱을 하면서 프린트할텐데, 이것을 과연
돌리면 어떤일이 일어나느냐 (인티저 오버플로우) 여기까지는 내가 무슨짓을 했는지
알수있겠는데 여기선 왜 갑자기 이게 음수가 되고, 이 다음엔 왜 갑자기 양수가 되고
이 다음부턴 무슨일이 일어나느냐? 이건 내가 원하는 결과가 아니잖아. 여기까지는
0이 두개씩 붙었고 그 다음도 0이 두개 붙는데, 이 다음은 왜 내가 원하는 결과가
안나오는가? 이런이리 발생하면 컴퓨터를 어떠ㄱㅎ게 해야하는가? 컴퓨터를 갔다
버려야죠? 근데 이럴떄마다 컴퓨터를 버리면 작동하는 컴퓨터가 거의 없을ㄷ텐데
어떡해. 내가 원하는거랑 실제 결과가 다르면 어떻게 해야한ㄴ가? 프로그래머
입장에선 내가 안에 어떤 서킷이 있는지 아무것도 몰라. 내가 프로그램을 하지만
여기서 어떤일이 일어나고있는지 아무것도 몰라, 이런걸 할수있는것엔 한계가 있다.

이제 여러분한테 원하는건 이런일이 일어나지 않기 위해선 컴퓨터 시스템이 어떻게
돌아가는건지 좀 알려줘야겠다 이런거야. 만약 숫자를 손으로 쓴다고 하면 자릿수에
제한이 없지만 컴퓨터가 가지고 계산을 할수있는 숫자는 **Word**로 제한이 되어있다.
일정한 크기가 넘어가면 이쪽에 있는 비트들은 없어져버리는거야. 그거를 왜
위에있는걸 버리나? 밑에있는걸 버리면 더 좋을텐데? 혹은 왜 정수오버플로우가
일어나면 왜 컴퓨터가 말을 안해주나?

이제 이런일을 막기위해서 부동소수점 연산도 나왔다. 이러면 어느정도는 내가 원하는
결과를 얻을수있지. 그런걸 만들기위해선 밑에 돌아가는 원리를 알아야한다

### Memory System

*Builder's Perspective*

CPU, 레지스터, L1 data-cache, L1 instruction-cache, L2 unified cache, RAM, Disk

i-cache라는건 내가 다음에 실행할 명령어가 무엇인지 미리 저장해놓은것, 데이타
캐쉬는 내가 어떤걸 읽어서 어떤걸 쓸건지가 저장된것이 데이타 캐쉬.

보통 L1캐쉬는 자기혼자쓰고, 보통 L2캐쉬는 2~4개 코어가 같이 쓰더라. 그리고
L1에선 d캐쉬 i캐쉬가 따로있지만 L2에선 구분없이 같이쓰더라. 여기까진 L2밖에
없지만 이제 L3, L4가 있기도 하더라. 그리고 요즘은 디스크가 없이 SSD가 있는경우도
있더라. 이제 이런건 컴퓨터를 만드는사람의 입장. CPU는 얼마나 좋아야 하는가,
캐쉬와 램은 얼마나 커야하는지, Disk는 하드를 달건지 NAND Flash를 달건지 등등
여러가지를 결정해야한다. 캐쉬도 **라이트백 캐쉬, 라이트 스루 캐쉬**, **다이렉트
맵드, 인덱스드**, 메모리도 **동기, 비동기**, **가상 인덱싱, 피지컬 인덱싱** 등등
고려할게 많다.

*Programmer's Perspective*

프로그래머 입장에선 CPU가 있고 내가 쓸수있는 메모리가 얼마냐가 중요하죠. 근데
그렇다고 이제 내가 L1 L2 RAM 이런걸 다 몰라도 되느냐. 사실 이걸 안다고
도움된다고 생각되지 않을수도 있다. 하지만 이제 이걸 봐라.

(캐쉬 프렌들리한 프로그램 짜는 예시)

똑같이 2048*2048 매트릭스를 카피를 해도 row-wise로 카피하는거랑 column-wise하게
카피하는게 전혀 성능이 다르지않는가. (i7 2.7GHz에서 실험했을때 30배 느려짐) 이게
성능이 전혀 똑같다면 내가 메모리 구조를 전혀 신경 안써도 되겠지? 하지만 현실은
그리 녹록치 않다.

이제 이런걸 알면 내가 액세스하는 메모리는 다 똑같은데, 액세스 하는 방법에 따라
속도가 달라지는걸 볼수있다. 이렇게 속도차이가 많이나면 속에서 뭔가 메모리를
단순히 액세스하는거 외에 뭔가 한다는걸 알수있다 (캐싱). 이 숫자를 한번 줄여보자.
2048이 아니라 100, 200, 300, 400 등등 크기를 바꿔가며 또 해보자. 어떤 차이가
있을까? (캐시 바운더리)

결국 저 하드웨어 사이즈를 알수밖에 없다. 저 L1 데이터캐쉬 사이즈가 얼마인지.
L2로 가면 느려지지. L3로 가면 더 느려지고 RAM으로 가면 더더욱 느려지겠지. 지금
이 램이라는건 우리는 마치 이차배열을 이차원공간처럼 쓰지만 사실 이건 선형이다.
내가 이걸 row-wise로 하면 선형으로 쭉 읽겠지만 column-wise로 하면 내가 이 선형
메모리를 전체를 계속 훑겠지. 자 이럴때 보통 캐쉬는 한번 이곳을 읽으면 그 근처를
64바이트를 통쨰로 읽고, 쓸떄도 똑같이 한다. 이떄 여기서 전체를 계속 stride로 훑으면
중요한 memory bandwidth를 낭비하는거지. 이 현상이 왜 일어나느지, 어떻게
해결하는지를 알으려면 결국 이 메모리 하드웨어 구조를 알아야하는거야.

### 첫번쨰 숙제

앞으로 학생들이 주로 사용할 컴퓨터를 하나씩 정하세요. 그 다음에, 그 컴퓨터를
사용해서 방금 비슷한 프로그램을 짜서 (cache 프렌들리 예제) 이런식으로 버전을
두개 짜서 i j 순서가 다른것이 영향을 주는 예제를 짜봐. 이걸 실제로 크기를
바꿔가면서 해보면 L1~L2, L2~L3, L3~RAM 사이의 간격을 볼수있어. (계단식 그래프를
그림) 이걸 하나 그려보는게 첫번째 숙제다.

여러분들 종강할때 어느정도 레벨이 되려면 이 계산 돌리는걸 직접 하지말고 스크립트
짜서 자동화하세요. 이걸 그려보면 여러분의 캐쉬 사이즈가 대충 어느정도인지
가늠할수있을거야. 그리고 여러분 컴퓨터 스펙이랑 비교해서 얼마나 들어맞았는지
비교해봐.

굉장히 복잡하게 들리지만 사실 그렇지 않아. 여러분 컴퓨터가 너무 일을 많이해서
불쌍하다 싶으면 캐쉬 바운더리 근처만 돌려봐.

**다음주 화요일 실습시간까지**

### Memory Mountain

이쪽은 메모리 크기고, 이쪽은 메모리 스트라이드. 높이는 스루풋 (초당 얼마나 많이
읽느냐). 여러분이 숙제 1을 하면 이 메모리 마운틴을 그려볼수 있는거야. 그러면 L1
L2 크기가 얼마나 되는지 미루어 짐작할수 있겠지.

### Lecture Coverage

* Data representation
* IA32 & x86-64 asm
* Program optimization
* Memory Hierarchy
* Linking
  * With DLL
* Exceptional Control Flow
* Virtual Memory
* Application level concurrency
* I/O and network programming

### Labs

* Key teaching insight:
  * Cool labs => Great Course
* A set of 1 and 2 week labs define the course.
* 1~2주에 랩 하나씩 할거다.

1. Data lab
1. Bomb lab
1. Buffer lab
1. Performance lab
1. Shell lab
1. Malloc lab
1. Proxy lab

### Architecture

* Y86 명령어셋을 다 알아야한다 (간단한 IA32)

> 3월 5일

링킹
--------

메인이라는 함수가 있고 스왑이라는 함수가 있다. 어떻게 이 두개를 하나의
프로그램으로 붙일까? 그냥 소스를 하나로 concat 할수도있겠지. 근데 그러면 큰
의미가 없겠지? 이걸 컴파일 하고 컴파일된 결과를 어떻게 한개로 만들까?

### Static Linking

```
gcc -O2 -g -o p main.c swap.c
./p
```

main.c -> `cpp, cc1, as` -> main.o
swap.c -> `cpp, cc1, as` -> swap.o
main.o, swap.o -> `ld` -> p

*.c : 소스
*.o : separately compiled relocatable object files
p : executable, fullly linked, object file
    (contains code and data for all functions defined in main.c and swap.c)

### Why Linkers?

왜 링크가 필요할까?

1.  **증분빌드**. 프로그램의 일부만 고쳤을때 전체 리빌드를 하지
    않기위해서, 모듈 디자인을 하기 위해서.

    우리가 제일 많이 쉽게볼수있는게 리눅스 컴파일과정이야. 파일이 수백개가 있는데
    전부 다 컴파일하려면 수백개를 다시해야하지? 근데 이걸 일부를 고친다고 그
    몇시간을 다시 거친다는거는 무서운 일이지.

    **라이브러리**를 만들 수도 있지. 자주 쓰는 함수들을 미리 라이브러리로 만들어놓고,
    나중에 이걸 그냥 링크해서 쓸 수 있도록 만들 수 있겠지

2.  **Efficiency**

    Time: Separate compilation

    Space: Libraries

    라이브러리를 링크했을때 너가 그 라이브러리의 모든함수들을 다 쓰느냐. 그렇지
    않아, 링크과정에서 이 안쓰는 함수들을 뺼 수 있다.

### What does linker do

1.  Symbol resolution

    컴파일된 C 코드는 함수호출이 있는것은 알지만 이게 어느 어드레스의 함수인지는
    아직 모르지. 전역변수와 같것도 마찬가지지. 이걸 정해주는것이 링커의 역할

    ```
    void swap() { }
    swap();
    int *xp = &x;
    ```

2.  Relocation

    오브젝트파일이 여기에 100바이트, 여기에 200바이트 있을때 이걸 하나로
    합쳐줘야겠지. 근데 합쳐주는과정에서 여러가지 위치들이 바뀌겠지. 그리고 이걸
    실제로 실행하려고 메모리에 올릴때에 또 위치가 바뀌겠지. 그런 위치를 어떻게
    바꿀지 여기엔 10을 더한다 여기엔 100을 더한다, 레퍼런스들을 나중에 고칠수
    있도록 하는것이 링커의 역할

### Three kinds of object files (modules)

1.  `.o` Relocatable object file

1.  `a.out` Executable object file

1.  `.so` Shared object file

    여러 프로그램들이 공유하는 오브젝트파일. 로드타임이나 실행타임에 동적으로
    링크됨.

    윈도우에서는 `dll`, OS X 에선 `dylib`이라고 불림.

### Executable and Linkable Format (ELF)

* Standard binary format for object files

오브젝트 파일은 어떻게 만들어야 하는 Rule 이다. AT&T System V Unix 에서 만들어져
계속 쓰이는것이다.

### ELF Object file format

1.  Elf header

    워드 사이즈, 바이트 순서, 파일타입 (`.o`, exec, `.so`), 머신타입, 등

1.  Segment header table

    페이지 크기, virtual addresses memory segments (sections), segment sizes

1.  .text section: 코드
1.  .rodata section: readonly data (jump tables, ...)
1.  .data section: Initialized global variables
1.  .bss section

    Uninitialized global variables, ...

    실제로 실행되면 공간을 차지하지만, 오브젝트 파일에서는 차지할 공간의 크기,
    이름만 들어있지만 실행되는순간 메모리가 잡힘.

    "Block Started by Symbol", "Better Save Space"

1.  .symtab section

    symbol table. 주로 프로시저 이름, static variable name, section name, 등

1.  .rel.text section

    코드 세그먼트에 대한 relocation 정보. 코드에 들어있는 variable 에 대한
    reference들, 실행되면 위치를 바꿔줘야하는 정보들이 여기에 들어있다.
    일반적으로 이런걸 컴파일할때 제일 많이쓰는 방법은 data section에서 +100번지,
    현재 program counter에서 -100번지 등 현재 정해져있는 위치의 offset을
    사용한다.

1.  .rel.data section

    데이터 섹션에 대한 relocation 정보. 코드와 마찬가지로 실행되면 위치가
    바뀌어야 하는것들에 대한것들

1.  .debug section

    디버그심볼이 들어이씀

1.  섹션 헤더 테이블

    각각의 섹션의 오프셋과 크기

### Linker Symbols

*   Global symbols

    내가 쓰고, 다른 모듈에도 보이는 심볼

*   External symbols

    내가 쓰지만, 다른 모듈에서 정의된 심볼

*   Local symbols

    내가 정의하고 나만 쓰는 심볼

### Resolving Symbols

```c
// main.c
int buf[2] = {1, 2}; // Global

int main() // Global
{
  swap(); // External
  return 0;
}
```
```c
// swap.c
extern int buf[]; // External

int *bufp0 = &buf[0]; // Global
static int *bufp1; // Local

void swap() // Global
{
  int temp; // Linker knows nothing of temp

  bufp1 = &buf[1];
  temp = *bufp0;
  *bufp0 = *bufp1;
  *bufp1 = temp;
}
```

### Relocating Code and Data

표준 라이브러리

main.o

.text에 main() 코드가 들어가고
전역변수가 .data에 들어가고

swap.o

.text에 swap() 코드가 들어각
bufp0 가 .data에 들어가고
bufp1는 .bss 에 들어감. swap의 private 심볼이지만, bss에 들어감

이걸 링크하면

.text에 헤더, 시스템 코드, 메인, 스왑, 기타 시스템 코드

.data에 시스템 데이터, buf, bufp0

.bss에 bufp1

그밑에 .symtab, .debug

### Relocation Info (main)

objdump 떠서 보는것보단 -S 옵션줘서 어셈블리 파일 보는게 편함

PC relative addressing. 코드 안에서 점프할때, immediate 변수를 쓸때엔 이걸 씀

그 외에, Data segment에서 변수를 가져다 쓸때엔 .data 기준으로 오프셋

### Executable before/after relocation (.text)

relocation 하기 전에는 함수의 정보들이 main+12, asdf+x 이런식으로
들어있는데, relocation 한 이후엔 정확히 함수를 가리킴

### Strong and Weak symbols

*   Strong: Procedures and initialized globals. `.data` 에 들어감. object 파일
    안에 위치가 다 정해져있음
*   Weak: Uninitialized globals. `.bss` 에 들어감. 위치가 정해져있지 않고,
    메모리에 올라갈때 메모리가 정해짐

### Linker's Symbol Rules

1.  Multiple strong symbols are __not allowed__

    Each item should be defined only once. Otherwise; **Linker error**.

1.  Strong symbol과 weak symbol이 같이있을경우, strong symbol을 선택함.

    ```c
    // p1.c
    int foo = 5;
    p1() {

    }
    ```
    ```c
    // p2.c
    int foo; // <- p1의 foo 가 strong 이어서, 이 foo는 무시됨.
    p2 () {

    }
    ```

1.  Weak symbol이 여러개일경우, 링커 마음대로.

### Linker puzzles

`int x; p1(){}`, `p1(){}`: 에러, `p1`

`int x; p1(){}`, `int x; p2(){}`: OK

`int x; int y; p1(){}`, `double x; p2(){}`: **Evil**, writes to x in p2 might
overwite y

`int x=7; int y=5; p1() {}`, `double x; p2() {}`: Nasty, writes to x in p2 will
overwrite y

`int x=7; p1(){}`, `int x; p2() {}`: OK

### Nightmare scenario

Two identical weak structs, compiled by differenct compilers with different
alignment rules.

### Role of `.h` files

```c
// global.h
#ifdef INITIALIZE
int g = 23;
static int init = 1;
#else
int g;
static int init = 0;
#endif
```

`#ifdef` 매크로는 여러 하드웨어를 동시에 지원하기 위해서 만들어졌음.

`-DINITIALIZE` 옵션으로 같은 소스코드로 여러 프로그램을 만들 수 있음

### Global Variables

*   Avoid if you can
    - Side effect!
    - Scope does matter
    - 아까 나온 Weak symbol, strong symbol 문제
*   Instead,
    - Use `static` if you can
    - Initialize if you define a global variable
    - Use `extern` if you use external global variable

### Packaging commonly used functions

* How to package functions commonly used by programmers?
  * Math, I/O, memory managements, string manipulation, etc.

이걸 어떻게 패키징하는게 좋을까? 링킹을 함으로써 이것들을 가능케 할수 있다.

1.  함수들을 한 파일에 전부다 집어넣는다.

    그 `.o` 파일을 다른데서 링크하면 되지.

    근데 공간/시간 비효율적임

2.  그냥 여러 파일에 함수들을 퍼트려놓음.

    프로그래머가 힘들어짐

### Solution: Static Libraries

`.a`, archive files

*   잘쓰는 함수들이 들어있는 오브젝트 파일들을 전부 붙여놓음. 그리고 맨 앞에
    인덱스를 놓아서 이 함수가 어느 주소에 있는지 표시해서 필요한 함수만 가져가서
    링크할 수 있도록 함

```sh
ar rs libc.a atoi.o printf.o ... random.o
```

역시 증분 업데이트를 지원하고, 뒤에 필요한게 더 생기면 집어넣으면 됨

### Commonly Used Libraries

`libc.a` C 표준 라이브러리. 8MB, 1392 오브젝트

`libm.a` 수학 라이브러리. 1MB, 401 오브젝트

```sh
ar -t /usr/lib/libc.a | sort

# ...
# fpritf.o
# fpu_contro.o
# fputc.o
# ...
```

### Linking with static libraries

main2.o src.o libc.a libvector.a -> `ld` -> exe

### Using Static Libraries

링커를 호출했을때 나열된 `.o`, `.a` 파일들의 심볼을 순서대로 리졸브 시키고,
못찾은게 뭐가있는지 기억했다가 거기부터 리졸브를 해나감. 끝까지 다했는데
리졸브를 못하면 뭔가 잘못된거.

* Problem
  * Command line order matters!
  * Moral: put libraries at the end of the command line.

    ```bash
    gcc -L. libtest.o -lmine
    gcc -L. -lmine libtest.o # <- Undefined reference to libfun
    ```