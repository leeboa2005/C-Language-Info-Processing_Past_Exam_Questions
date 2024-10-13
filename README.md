
 ## 정보처리기사 C언어 기출 문제 모음
**20년 1회**

```c
#include <stdio.h>
 
main() {
  int c=1;
  switch(3){
    case 1:c+=3;
    case 2:c++;
    case 3:c=0;
    case 4:c+=3;
    case 5:c-=10;	
    default : c--;
    
  }
printf("%d",c);
  }
```
<details>
<summary>✅ 정답</summary>

-8
</details>
<br>

🖋 **문제 풀이** <br><br>
switch(3): 3에 해당하는 case부터 실행 <br>
case 3: c = 0; → c는 0  <br>
case 4: c += 3; → c는 3 <br>
case 5: c -= 10; → c는 -7  <br>
default: c--; → c는 -8 <br>


<hr> 

**20년 1회**

```c
#include <stdio.h>
void align(int a[]){
  int temp;
  for(int i=0;i<4;i++)
    for(int j=0;j<4-i;j++)
      if(a[j]>a[j+1]){
        temp=a[j];
        a[j]=a[j+1];
        a[j+1]=temp;
      }
}
 main() {
   int a[]={85, 75, 50, 100, 95};
   align(a);
   for(int i=0;i<5;i++)
     printf("%d",a[i]);
}
```

<details>
<summary>✅ 정답</summary>
	
50758595100
</details>
<br>


🖋 **문제 풀이** <br><br>
align 함수가 작동하는 과정<br> <br>
**1회전 (i = 0)** <br>
j = 0: 85 > 75 → 교환: {75, 85, 50, 100, 95}  <br>
j = 1: 85 > 50 → 교환: {75, 50, 85, 100, 95}  <br>
j = 2: 85 > 100 → 교환 없음: {75, 50, 85, 100, 95}  <br>
j = 3: 100 > 95 → 교환: {75, 50, 85, 95, 100} <br> <br>
**2회전 (i = 1)**  <br>
j = 0: 75 > 50 → 교환: {50, 75, 85, 95, 100}  <br>
j = 1: 75 > 85 → 교환 없음: {50, 75, 85, 95, 100}  <br>
j = 2: 85 > 95 → 교환 없음: {50, 75, 85, 95, 100}  <br> <br>
**3회전 (i = 2)**  <br>
j = 0: 50 > 75 → 교환 없음: {50, 75, 85, 95, 100} <br>
j = 1: 75 > 85 → 교환 없음: {50, 75, 85, 95, 100} <br> <br>
**4회전 (i = 3)**  <br>
j = 0: 50 > 75 → 교환 없음: {50, 75, 85, 95, 100} <br>
최종적으로 정렬된 배열은 {50, 75, 85, 95, 100}입니다. <br>



<hr> 

**20년 3회**

```c
#include <stdio.h>
int r1(){
  return 4;
}
int r10(){
  return(30+r1());
}
int r100(){
  return(200+r10());
}
int main(){
  printf("%d\n",r100());
}
```
<details>
<summary>✅ 정답</summary>
234
</details>
<br>


🖋 **문제 풀이** <br><br>
함수 호출 순서 <br>
r10()은 30 + 4 계산 → 34 반환<br>
r100()은 200 + 34 계산 → 234 반환<br>
main 함수에서 234 출력

<hr> 

**20년 4회**

```c
#include <stdio.h>
 
 main() {
   char *p="KOREA";
   printf("%s\n",p);
   printf("%s\n",p+3);
   printf("%c\n",*p);
   printf("%c\n",*(p+3));
   printf("%c\n",*p+2);
   }

```
<details>
<summary>✅ 정답</summary>
KOREA<br> 
EA<br> 
K<br> 
E<br> 
M 
</details>
<br>

🖋 **문제 풀이** <br><br>
1. 첫 번째 출력: 포인터 p가 가리키는 문자열 전체를 출력합니다. 결과는 KOREA입니다. <br>
2. 두 번째 출력: 포인터 p에서 3번째 위치로 이동하여 그 위치부터 시작하는 부분 문자열을 출력합니다. 결과는 EA입니다. <br>
3. 세 번째 출력: 포인터 p가 가리키고 있는 첫 번째 문자를 출력합니다. 결과는 K입니다.<br>
4. 네 번째 출력: 포인터 p에서 3번째 위치의 문자를 출력합니다. 결과는 E입니다.<br>
5. 다섯 번째 출력: 포인터 p가 가리키는 첫 번째 문자 'K'의 ASCII 값에 2를 더한 값을 출력합니다. 결과는 문자 'M'입니다.

<hr> 

**21년 1회**

```c
#include <stdio.h>
void main(){
struct insa {
	char name[10];
    int age;
 }a[] = {"Kim",28,"Lee",38,"Park",42,"Choi",31};
    struct insa *p;
    p = a;
    p++;
    printf("%s\n", p-> name);
    printf("%d\n", p-> age);
  }

```

<details>
<summary>✅ 정답</summary>
Lee <br>
38 <br>
</details>
<br>

🖋 **문제 풀이** <br><br>
1. 사람의 이름과 나이를 저장하기 위해 구조체 정의한다. <br>
2. 정의한 구조체를 사용하여 여러 사람의 정보를 담는 배열 생성 <br>
3. 포인터 선언하고, 배열의 첫 번째 요소를 가리키도록 초기화 <br>
4. 포인터를 한 칸 이동시켜 두 번째 요소를 가리킴 <br>
6. 현재 포인터가 가리키는 사람의 이름과 나이 출력 <br>
7. 결과적으로 두 번째 사람인 "Lee"와 그의 나이인 38 출력 

<hr> 

**21년 2회**

```c
#include <stdio.h>
int main(){
   int res;
   res = mp(2,10);
   printf("%d",res);
   return 0;
}
 
int mp(int base, int exp) {
   int res = 1;
   for(int i=0; i < exp; i++){
      res *= base;
   }
   
   return res;

```

<details>
<summary>✅ 정답</summary>
1024
</details>
<br>

🖋 **문제 풀이** <br><br>
1회차: res = 1 X 2 = 2  <br>
2회차: res = 2 X 2 = 4  <br>
3회차: res = 4 X 2 = 8  <br>
4회차: res = 8 X 2 = 16  <br>
5회차: res = 16 X 2 = 32  <br>
6회차: res = 32 X 2 = 64  <br>
7회차: res = 64 X 2 = 128  <br>
8회차: res = 128 X 2 = 256  <br>
9회차: res = 256 X 2 = 512  <br>
10회차: res = 512 X 2 = 1024 

<hr>

**21년 2회**


```c
#include <stdio.h>
int main(){
 
int ary[3];
int s = 0;
*(ary+0)=1;
ary[1] = *(ary+0)+2;
ary[2] = *ary+3;
for(int i=0; i<3; i++){
  s=s+ary[i];
}
 
printf("%d",s);
 
}
```

<details>
<summary>✅ 정답</summary>
8
</details>
<br>

🖋 **문제 풀이** <br><br>
1. 정수형 배열 ary를 크기 3으로 정의<br>
2. 합계를 저장할 변수 s를 0으로 초기화<br>
3. 배열의 첫 번째 요소에 1을 저장한다 (ary[0] = 1).<br>
4. 배열의 두 번째 요소에 첫 번째 요소에 2를 더한 값을 저장(ary[1] = 1 + 2, 따라서 ary[1] = 3).<br>
5. 배열의 세 번째 요소에 첫 번째 요소에 3을 더한 값을 저장(ary[2] = 1 + 3, 따라서 ary[2] = 4).<br>
6. 반복문을 사용하여 배열의 모든 요소를 순회하며 합계 s에 각 요소의 값을 합산<br>
7. 최종적으로 s의 값을 출력


<hr>

**21년 3회**

``` c
#include <stdio.h>
 
int main(){
int *arr[3];
int a = 12, b = 24, c = 36;
arr[0] = &a;
arr[1] = &b;
arr[2] = &c;
 
printf("%d\n", *arr[1] + **arr + 1);
 
}
```
<details>
<summary>✅ 정답</summary>
37 
</details>
<br>

🖋 **문제 풀이** <br><br>
1. 정수형 포인터 배열 arr를 크기 3으로 정의한다.<br>
2. 정수형 변수 a, b, c를 각각 12, 24, 36으로 초기화한다.<br>
3. 포인터 배열 arr의 각 요소에 변수 a, b, c의 주소를 저장한다:<br>
  - arr[0]에는 a의 주소,<br>
  - arr[1]에는 b의 주소,<br>
  - arr[2]에는 c의 주소가 저장된다.<br>
4. ***arr[1]**은 b의 값을 참조하므로 **24**가 된다.<br>
****arr은 arr[0]**이 가리키는 a의 값을 참조하므로 **12**가 된다.<br>
5. 전체 식은 **24 + 12 + 1**이 되어 37이 된다.

<hr>

**21년 3회**

```c
#include <stdio.h>
 
struct jsu {
  char name[12];
  int os, db, hab, hhab;
};
 
int main(){
struct jsu st[3] = {{"데이터1", 95, 88}, 
                    {"데이터2", 84, 91}, 
                    {"데이터3", 86, 75}};
struct jsu* p;
 
p = &st[0];
 
(p + 1)->hab = (p + 1)->os + (p + 2)->db;
(p + 1)->hhab = (p+1)->hab + p->os + p->db;
 
printf("%d\n", (p+1)->hab + (p+1)->hhab);
}

```

<details>
<summary>✅ 정답</summary>
501 
</details>
<br>

🖋 **문제 풀이** <br><br>
1. 구조체 정의: jsu라는 구조체를 정의한다. 이 구조체는 이름(name), 운영체제 점수(os),<br> 데이터베이스 점수(db), 하드웨어 점수(hab), 하드웨어 최고 점수(hhab)를 저장한다. <br>
2. 구조체 배열 초기화: st라는 jsu 구조체 배열을 크기 3으로 정의하고, 각각의 요소를 초기화한다.<br><br>

3. 각 구조체 요소의 내용 <br>

| 인덱스 | 이름     | os  | db  |
|--------|----------|-----|-----|
| 0      | 데이터1 | 95  | 88  |
| 1      | 데이터2 | 84  | 91  |
| 2      | 데이터3 | 86  | 75  |
<br> 

4. 하드웨어 점수 계산:<br>
(p + 1)->hab를 계산한다. 여기서 p + 1은 st[1]을 가리킨다. <br> hab는 st[1]의 하드웨어 점수로,<br> os인 84와 st[2]의 db인 75를 더한 값으로 설정된다.<br><br>
hab = 84 + 75 = 159 <br> 
하드웨어 최고 점수 계산:<br>
(p + 1)->hhab를 계산한다. hhab는 st[1]의 하드웨어 최고 점수로, <br> hab인 159와 st[0]의 os인 95, st[1]의 db인 91을 더한 값으로 설정된다.<br><br>
hhab = 159 + 95 + 91 = 345 <br> 
5. 최종 출력:<br>
printf를 통해 (p + 1)->hab + (p + 1)->hhab의 값을 출력한다.<br><br>
계산: 159 + 345 = 504<br>

<hr>

**22년 1회**

5를 입력받았을 때

```c
#include <stdio.h>
 
int func(int a) {
 if(a<=1) return 1;
 return a*func(a-1);
}
 
int main(){
 int a;
 scanf("%d",&a);
 printf("%d",func(a));
}
```
<details>
<summary>✅ 정답</summary>
120
</details>
<br>

🖋 **문제 풀이** <br><br>
주어진 입력이 5일 경우: <br>
func(5)가 호출 <br> <br>
계산 과정 <br>
func(5) = 5 X func(4) = 120  <br>
func(4) = 4 X func(3) = 24  <br>
func(3) = 3 X func(2) = 6  <br>
func(2) = 2 X func(1) = 2  <br>
func(1) = 1 (기저 사례)  <br>
따라서, 전체 계산은 5 * 4 * 3 * 2 * 1 = 120 

<hr>

**22년 1회**

아래 프로그램은 정수를 역순으로 출력하는데 (1)(2)(3)에 들어갈 연산자를 쓰시오

``` c
#include <stdio.h>
int main() {
 
  int number = 1234;
  int div = 10;
  int result = 0;
 
  while (number ( 1 ) 0) {
  
    result = result * div;
    result = result + number ( 2 ) div;
    number = number ( 3 ) div;
  
  }
 
  printf("%d", result);
return 0;
 
}
```
<details>
<summary>✅ 정답</summary>
(1) > (2) % (3) / 
</details>
<br>

🖋 **문제 풀이** <br><br>
목적 : 정수를 역순으로 출력 <br>
1. while 루프  <br>
while (number ( 1 ) 0)는 number가 0보다 큰 동안 반복합니다. 따라서 (1)에는 > 연산자가 들어갑니다. <br>
이 조건이 참일 때 루프가 계속됩니다. <br> <br>
2. 결과 계산 <br>
result = result * div;는 result의 값에 10을 곱합니다.  <br> 여기서 div는 10이기 때문에, result의 자리수를 하나 올리는 역할을 합니다. <br>
result = result + number ( 2 ) div;는 number의 마지막 자리수를 result에 추가합니다. <br> 여기서 (2)에는 % 연산자가 들어갑니다. %는 나머지를 구하는 연산자로,  <br> number % div는 number의 마지막 자리수를 가져옵니다. <br>
number = number ( 3 ) div;는 number를 10으로 나누어 마지막 자리수를 제거합니다.  <br> 여기서 (3)에는 / 연산자가 들어갑니다.

<hr>
 
**22년 2회**


```c
#include <stdio.h>
struct A{
  int n;
  int g;
  };
 
int main() { 
struct A a[2];
  for(int i=0;i<2;i++){
    a[i].n=i, a[i].g=i+1;
  }
  printf("%d",a[0].n+a[1].g);
}
```

<details>
<summary>✅ 정답</summary>
 2
</details>
<br>

🖋 **문제 풀이** <br><br>
구조체 A는 두 개의 정수형 멤버 n과 g를 갖음. <br> 
a[0].n = 0, a[1].n = 1 <br> 
a[0].g = 1, a[1].g = 2 <br> 
a[0].n + a[1].g);  0 + 2  = 2 

<hr>

**22년 2회**


```c
#include <stdio.h>
 
int len(char*p);
 
int main(){
 
  char*p1 = "2022";
  char*p2 = "202207";  
  
  int a = len(p1);
  int b = len(p2);
  
  printf("%d", a+b);
 
}
 
int len(char*p){
  int r = 0;
  while(*p != '\0'){
    p++;
    r++;
  }
return r;
}
```
<details>
<summary>✅ 정답</summary>
 10
</details>
<br>

🖋 **문제 풀이** <br> <br>
1. 이 함수는 문자열의 길이를 계산합니다.<br>
포인터 p가 가리키는 문자열의 각 문자를 순회하며, <br>
문자열의** 끝('\0')에 도달할 때까지 r을 증가**시킵니다.<br><br>
2. 길이 계산<br>
`len(p1)` 호출 시 문자열 "2022"의 길이는 4입니다.<br>
`len(p2)` 호출 시 문자열 "202207"의 길이는 6입니다.<br><br>
3.  `printf("%d", a + b);`  출력: 4 + 6


<hr>

**22년 2회**

```c
#include <stdio.h>
 
int main(int argc, char*argv[]) {
  int a[4]={0,2,4,8};
  int b[3]={};
  int i=1;
  int sum=0;
  int *p1;
 
  for(i;i<4;i++){
    p1=a+i;
    b[i-1]=*p1-a[i-1];
    sum=sum+b[i-1]+a[i];
  }
  printf("%d",sum);
 
  return 0;
}
```
<details>
<summary>✅ 정답</summary>
22
</details>
<br>

🖋 **문제 풀이** <br> <br>
**1회차 (i = 1)** <br><br>
p1 = a + 1; → p1이 a[1] (2)을 가리킴 <br>
b[0] = *p1 - a[0] → b[0] = 2 - 0 = 2 <br>
sum = sum + b[0] + a[1] → sum = 0 + 2 + 2 = 4 <br> <br>
**2회차 (i = 2)** <br> <br>
p1 = a + 2; → p1이 a[2] (4)을 가리킴 <br>
b[1] = *p1 - a[1] → b[1] = 4 - 2 = 2 <br>
sum = sum + b[1] + a[2] → sum = 4 + 2 + 4 = 10 <br> <br>
**3회차 (i = 3)** <br> <br>
p1 = a + 3; → p1이 a[3] (8)을 가리킴 <br>
b[2] = *p1 - a[2] → b[2] = 8 - 4 = 4 <br>
sum = sum + b[2] + a[3] → sum = 10 + 4 + 8 = 22 <br>


<hr>

아래는 C언어의 2차원 배열 형태이다. field의 경우 2차원 배열 형태는 예시처럼 출력되므로, 이를 참고하여 mines의 2차원 배열 형태를 작성하시오. 

```c 
#include <stdio.h>
void main(){
 
int mines[4][4] = {{0,0,0,0},{0,0,0,0},{0,0,0,0},{0,0,0,0}};
int field[4][4] = {{0,1,0,1},{0,0,0,1},{1,1,1,0},{0,1,1,1}};
 
int w = 4, h = 4;
 
  for(int y=0; y<h; y++) {
      for(int x=0;x<w;x++) {  
        if(field[y][x] == 0) continue;
        for(int j=y-1;j<=y+1;j++) {
          for(int i=x-1;i<=x+1;i++) {
                  if(chkover(w,h,j,i) == 1) 
                     mines[j][i] += 1;
          }
        }
      }
    }
 }
 
int chkover(int w,int h,int j,int i) {
  if (i >= 0 && i < w && j >= 0 && j < h) return 1;
  return 0;
}
```

![](https://velog.velcdn.com/images/leeboa2003/post/ee702562-9b35-4e52-9ab0-8ee68ed366d7/image.png)

<details>
<summary>✅ 정답</summary>
1   1   3   2
3   4   5   3
3   5   6   4
3   5   5   3
</details>
<br>

🖋 **문제 풀이** <br> <br>
 field 배열에서 지뢰(1)가 있는 위치 주위의 칸에 지뢰 수를 세어서 mines 배열에 기록<br><br>
1. 배열 초기화<br><br>
- mines 배열: 각 칸의 지뢰 수를 저장 (초기값 0).<br>
- field 배열: 지뢰 위치 (1은 지뢰, 0은 없음).<br>
2. 이중 for 루프<br><br>
- field 배열을 순회하면서 지뢰가 있는 칸(1)을 찾는다.<br>
- 지뢰가 있는 칸 주변 3x3 영역을 검사하여 mines 배열의 해당 칸 값을 증가<br>
3. chkover 함수<br><br>
주어진 인덱스가 배열 범위를 벗어나지 않는지 확인. <br><br>
간단한 예시 <br>
- field 배열<br>
0 1 0 1 <br>
0 0 0 1 <br>
1 1 1 0 <br>
0 1 1 1 <br><br>
지뢰 주변 수 계산<br>
- (0,1) 주변: (0,0)(0,2)(1,0)(1,1)(1,2) → 지뢰 수 증가<br>
- (0,3) 주변: (0,2)(1,2)(1,3) → 지뢰 수 증가<br>
- 나머지 지뢰들도 같은 방식으로 처리.

<hr> 

**22년 3회**

```c
#include<stdio.h>
main(){
  int s, el =0;
  for(int i=6; i<=30; i++){
    s=0;
    for(int j=1; j<=i/2; j++){
      if(i%j==0){
        s=s+j;
      }
    }
    if(s==i){
    el++;
    }
  }
  printf("%d", el);
  }
```


<details>
<summary>✅ 정답</summary>
2
</details>
<br>

🖋 **문제 풀이** <br> <br>
완전수 구하는 문제 <br>
📄 완전수 : 자기 자신을 제외한 약수의 합이 자기 자신과 같은 자연수를 의미 <br>
1. 6부터 30까지의 수를 순회
   
```c
for(int i=6; i<=30; i++){
```
<br>
2. 약수 합 계산 <br>

```c
s=0;
for(int j=1; j<=i/2; j++){
    if(i%j==0){
        s=s+j;
    }
}
```
<br>
3. 완전수 확인

```c
if(s==i){
    el++;
}

``` 


<hr> 

**23년 1회**


```c
#include <stdio.h>
 
int main(void) {
  char a[]="Art";
  char*p=NULL;
  p=a;
  printf("%s\n",a);
  printf("%c\n",*p);
  printf("%c\n",*a);
  printf("%s\n",a);
 
  for(int i=0;a[i]!='\0';i++){
    printf("%c",a[i]);
  }
}

```
<details>
<summary>✅ 정답</summary>
Art
A
A
Art
Art
</details>
<br>

🖋 **문제 풀이** <br> <br>
**%s는 문자열 전체를 출력**하고, **%c는 개별 문자**를 출력<br>
- p라는 포인터를 선언하고, a의 주소를 p에 저장합니다. 이제 p는 문자열 "Art"를 가리킵니다.<br>
- printf("%s\n", a);: 문자열 a를 출력합니다. 결과는 Art.<br>
- printf("%c\n", *p);: 포인터 p가 가리키는 첫 번째 문자를 출력합니다. 결과는 A.<br>
- printf("%c\n", *a);: 배열 a의 첫 번째 문자를 출력합니다. 결과는 A.<br>
- printf("%s\n", a);: 다시 문자열 a를 출력합니다. 결과는 Art.<br>

<hr>

**23년 1회**

``` c 
#include <stdio.h>
 
int main(void) {
  char *a = "qwer";
  char *b = "qwtety";
  for (int i = 0; a[i] != '\0'; i++) {
    for (int j = 0; b[j] != '\0'; j++) {
      if (a[i] == b[j]) printf("%c", a[i]);
    }
  }
}

```
<details>
<summary>✅ 정답</summary>
qwe
</details>
<br>

🖋 **문제 풀이** <br> <br>
- a의 첫 번째 문자 'q'와 b의 문자들 중 'q'와 비교되어 일치하므로 출력됩니다.<br>
- 다음으로 a의 두 번째 문자 'w'도 b의 문자들 중 'w'와 일치하므로 출력됩니다.<br>
- a의 세 번째 문자 'e'는 b의 문자들 중 'e'와 비교되어 일치하므로 출력됩니다.<br>
- a의 네 번째 문자 'r'는 b의 문자들 중 'r'과 비교할 때 일치하지 않으므로 출력되지 않습니다.

<hr> 

**23년 1회**

다음은 이진수에서 십진수로 변환하는 코드이다.  (가)는 연산자이고 (나)는 정수일 때 빈칸을 알맞게 쓰시오.

```c
#include <stdio.h>
 
int main(void) {
int input = 101110;
int di = 1;
int sum = 0;
 
while (input > 0) {
sum = sum + (input (가)(나) * di);
di = di * 2;
input = input / 10;
}
 
printf("%d", sum);
 
return 0;
}
```
<details>
<summary>✅ 정답</summary>
(가) : % (나) : 10 또는 2
</details>
<br>

🖋 **문제 풀이** <br> <br>
1. 이진수 입력<br>
input은 이진수 형식으로 주어진 101110입니다. 이 값은 실제로는 10진수로 표현된 숫자입니다.<br>
2. 이진수 자리수 추출<br>
input % 10은 input의 가장 오른쪽 자리수를 추출합니다. 예를 들어, 처음에 input은 101110이므로 input % 10은 0이 됩니다. 이 값은 현재 자리의 이진수 값을 나타냅니다.<br>
3. 합계 계산<br>
이 자리수에 di를 곱하여 sum에 더합니다. di는 현재 자리의 2의 거듭제곱 값입니다. 처음에는 1 (2^0), 다음에는 2 (2^1), 그 다음에는 4 (2^2) 등으로 증가합니다.<br>
4. 자리수 증가 및 다음 자리로 이동<br>
di를 2배로 증가시키고, input을 10으로 나누어 다음 자리로 이동합니다. 이렇게 하면 오른쪽에서 왼쪽으로 이진수를 처리하게 됩니다.<br>
0 X 1 (1의 자리)<br>
1 X 2 (2의 자리)<br>
1 X 4 (4의 자리)<br>
0 X 8 (8의 자리)<br>
1 X 16 (16의 자리)<br><br>
이를 모두 더하면: 0 + 2 + 4 + 0 + 16 = 22
<hr>

**23년 1회**

(가) (나) 빈칸에 알맞은 변수를 쓰시오.

```c                                                                                                               
#include <stdio.h>
 
void swap(int* idx1, int* idx2) {
  
  int t = *idx1;
  *idx1 = *idx2;
  *( 가 ) = t;
}
void Usort(int a[], int len) {
  for (int i = 0; i < len - 1; i++) {
    for (int j = 0; j < len - i - 1; j++) {
      if (a[j] > a[j + 1])
        swap(&a[j], &a[j + 1]);
    }
  }
 
  for (int k = 0; k < 5; k++) {
    printf("%d ", a[k]);
  }
}
 
int main(void) {
  int arr[] = {64, 34, 25, 12, 40};
  int nx = 5;
 
  Usort(arr, (나));
  return 0;
}
```

<details>
<summary>✅ 정답</summary>
(가) idx2 (나) nx
</details>
<br>

🖋 **문제 풀이** <br> <br>
버블  정렬(Bubble Sort) 알고리즘 <br>
- swap 함수는 두 정수 포인터가 가리키는 값을 서로 교환하는 역할.<br>
-  *(가)는 *idx2입니다. 이렇게 하면 첫 번째 포인터가 가리키는 값이 두 번째 포인터가 가리키는 값으로 대체<br>
- Usort 함수는 배열 a의 길이를 len으로 받아서 버블 정렬을 수행<br>
- 두 개의 중첩 루프를 사용하여 배열의 요소를 비교하고, <br>큰 값을 뒤로 보내는 방식으로 정렬 -> 정렬 끝난 후 배열의 첫 5개 요소 출력 <br>
- (나)에는 배열의 길이인 nx가 들어가야 합니다. 즉, Usort(arr, nx);로 호출.<br>
<hr>

**23년 2회**

입력값이 순서대로 5, 4, 3, 2, 1일 경우 출력값이 43215로 출력 되도록 빈칸(가)에 들어갈 코드를 작성하시오.

```c
int main()
{
    int n[5];
    int i;
    
    for(i=0;i<5;i++){
        printf("숫자를 입력하세요 : ");
        scanf("%d",&n[i]);
    }
    
    for(i=0;i<5;i++){
        printf("%d",(가));
    }
 
    return 0;
}
```
<details>
<summary>✅ 정답</summary>
 n[(i+1) % 5]
</details>
<br>

🖋 **문제 풀이** <br> <br>
첫번째 요소가 마지막으로가고 나머지요소들은 앞쪽으로 한 자리씩 이동해야함 <br>
n[(1) % 5] = n[1] (2번째 요소)<br>
n[(2) % 5] = n[2] (3번째 요소)<br>
n[(3) % 5] = n[3] (4번째 요소)<br>
n[(4) % 5] = n[4](5번째 요소)<br>
n[(5) % 5] = n[5] (1번째 요소)<br>


<hr>

**23년 2회**
a,b,c,d의 빈칸에 알맞은 식을 <보기>에서 찾아쓰는데 <보기>를 최소한으로 쓰시오.

<보기> <br>
1000  <br>
500  <br>
100  <br>
10 <br>
% <br>
/ <br>
+ <br>
-

```c
#include<stdio.h> 
 
int main()
{
int m=4620;
int a,b,c,d;
a=(가)
b=(나)
c=(다)
d=(라)
printf("1000원 개수: %d",a);
printf("500원 개수: %d",b);
printf("100원 개수: %d",c);
printf("10원 개수: %d",d);
return 0;
}
```
<details>
<summary>✅ 정답</summary>
(가) : m / 1000 (나) : (m%1000)/500 (다) : (m%500)/100 (라) : (m%100)/10
</details>
<br>

🖋 **문제 풀이** <br> <br>
**(가): m / 1000**  <br>
1000원 단위의 개수를 구합니다. m을 1000으로 나누면 1000원 동전의 개수를 얻을 수 있습니다.
예: 4620 / 1000 = 4, 즉 1000원이 4개입니다.<br> <br>
**(나): (m % 1000) / 500**
500원 단위의 개수를 구합니다. 먼저 m을 1000으로 나눈 나머지(m % 1000)를 계산한 다음, <br> 그 값을 500으로 나누어 500원 동전의 개수를 얻습니다.
예: 4620 % 1000 = 620, 620 / 500 = 1, 즉 500원이 1개입니다.<br> <br>
**(다): (m % 500) / 100** <br>
100원 단위의 개수를 구합니다. 먼저 m을 500으로 나눈 나머지(m % 500)를 계산한 다음, <br> 그 값을 100으로 나누어 100원 동전의 개수를 얻습니다.
예: 4620 % 500 = 120, 120 / 100 = 1, 즉 100원이 1개입니다.<br> <br>
**(라): (m % 100) / 10** <br>
10원 단위의 개수를 구합니다. 먼저 m을 100으로 나눈 나머지(m % 100)를 계산한 다음, <br> 그 값을 10으로 나누어 10원 동전의 개수를 얻습니다.
예: 4620 % 100 = 20, 20 / 10 = 2, 즉 10원이 2개입니다.

<hr>

**23년 2회**

다음 문제에서 홍길동, 김철수, 박영희 순서대로 입력했다고 할 때 출력결과

```c
#include<stdlib.h> 
 
char n[30];
 
char *test() {
printf("입력하세요 : ");
gets(n);
return n;
}
 
int main()
{
char * test1;
char * test2;
char * test3;
 
test1 = test();
test2 = test();
test3 = test();
 
printf("%s\n",test1);
printf("%s\n",test2);
printf("%s",test3);
return 0;
}
```
<details>
<summary>✅ 정답</summary>
박영희
박영희
박영희
</details>
<br>

🖋 **문제 풀이** <br> <br>
**char n[30];로 선언된 배열 n은 모든 호출에서 동일한 메모리 공간을 사용**<br><br>
- 입력 순서 <br>
1번째 호출: test1에 "홍길동" 저장 (이때 n 배열에 "홍길동"이 저장됨)<br>
2번째 호출: test2에 "김철수" 저장 (이때 n 배열에 "김철수"가 저장됨, 이전 값인 "홍길동" 덮어씌움)<br>
3번째 호출: test3에 "박영희" 저장 (이때 n 배열에 "박영희"가 저장됨, 이전 값인 "김철수" 덮어씌움) <br><br>
- 출력 순서<br>
printf("%s\n", test1); → "홍길동" 출력 (첫 번째 호출에서 저장된 값)<br>
printf("%s\n", test2); → "김철수" 출력 (두 번째 호출에서 저장된 값)<br>
printf("%s", test3); → "박영희" 출력 (세 번째 호출에서 저장된 값, 이때 n의 값이 덮어씌워짐)<br><br>
- **왜 박영희가 3번 출력되는가?**<br>
  - 사실, test3에 저장된 값은 "박영희"입니다. 하지만 모든 변수 test1, test2, test3가 동일한 n 배열을 가리키기 때문에<br> 마지막 호출인 test()의 결과가 모든 변수에 영향을 미칩니다.<br>
  - 즉, test1, test2는 "박영희" 이전의 값인 "홍길동"과 "김철수"를 출력하지만,<br> test3는 마지막 입력인 "박영희"를 출력하게 됩니다. <br><br>
 - 해결 방법 ? <br>
   - 각 호출마다 서로 다른 배열을 사용하여 별도의 문자열을 저장하도록 수정해야 합니다. <br>예를 들어, char n1[30], n2[30], n3[30];와 같이 각각의 배열을 만들고,<br> 각 배열에 입력을 저장하도록 변경할 수 있습니다

<hr>

**23년 2회**

```c
#include<stdio.h>
 
int main(void)
{
    int n[3] = {73, 95, 82};
    int sum = 0;
    for(int i=0;i<3;i++){
        sum += n[i];
}
 
switch(sum/30){
  case 10:
  case 9: printf("A");
  case 8: printf("B");
  case 7: 
  case 6: printf("C");
  default: printf("D");
}
    return 0;
}
```

<details>
<summary>✅ 정답</summary>
BCD 
</details>
<br>

🖋 **문제 풀이** <br> <br>
- sum 은 250이라는 결과 값이 나오고, switch(sum/30) = switch(8)이나오게됨 <br>
- switch 문은 8에 해당하는 case로 진입한다.<br>
- case 8:가 실행되어 printf("B");가 호출된다.<br>
이후 case가 끝나지 않고 다음 case로 계속 진행되므로, printf("C");도 호출된다.<br>
case 6:과 case 7:는 조건을 만족하지 않지만, default:가 실행되어 printf("D");도 호출된다.

<hr>

**23년 2회**

```c
#include<stdio.h>
 
int main(void){
    int c=0;
    for(int i = 1; i <=2023; i++) { 
 
      if(i%4 == 0) c++; 
 
}
   printf("%d", c);
    return 0;
}
```
<details>
<summary>✅ 정답</summary>
505
</details>
<br>

🖋 **문제 풀이** <br> <br>
 4의 배수 구하기 <br>
- 1부터 2023까지의 숫자 중에서 4의 배수가 몇 개인지를 계산하고 출력<br>
- 4의 배수는 4, 8, 12, ..., 2020까지 포함되므로, 출력 결과는 505


<hr>

**23년 2회**

```c
#include<stdio.h>
#define MAX_SIZE 10
 
int isWhat[MAX_SIZE];
int point= -1; 
 
void into(int num) {
    if (point >= 10) printf("Full");
    isWhat[++point] = num;
}
 
int take() {
if (isEmpty() == 1) printf("Empty");
return isWhat[point--];
}
 
int isEmpty() {
    if (point == -1) return 1;
    return 0;
}
 
int isFull() {
    if (point == 10) return 1;
    return 0;
}
 
int main(int argc, char const *argv[])
{
    int e;
    into(5); 
    into(2);
    while(!isEmpty())
    {
        printf("%d", take());
        into(4); 
        into(1); 
        printf("%d", take()); 
 
        into(3); 
        printf("%d", take()); 
        printf("%d", take()); 
 
        into(6); 
        printf("%d", take()); 
        printf("%d", take()); 
    }
    return 0;
}
```
