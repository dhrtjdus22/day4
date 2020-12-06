DAY4
===================
# import
```
1. from ? import *
2. from ? import ?
3. import ? as ?
```
1. from random import *
> random에 있는 모든함수를 임포트

2. from random import randint
> random에 있는 함수중 randint만 임포트

3. import random as rnd
> rnd.randint() 와 같이 사용할수 있게됨   

-----------------------------------------------------------------------------
# 랜덤 메소드

### randint(a , b)   
> a부터 b 사이의 임의의 정수
   
### random( )   
> 0 부터 1 사이의 임의의 float
   
### uniform(a , b)   
> a부터 b사이의 임의의 float
   
### randrange( a, b, c)   
> a부터 b 사이의 c만큼 건너뛴 숫자들

### choice( a )   
> a리스트의 원소에서 아무 원소나 하나 뽑아줌

-----------------------------------------------------------------------------

# 슬라이싱(인덱스)삽입,삭제,치환

```list = [1,2,3,4,5] ```

### list[a:b] 
> list의 a번부터 b번까지의 숫자 
```list[ 0:2 ] -> [1,2,3]```

### list[ : 0] = [ ? ] 
> 리스트 맨 첫번째에 ?를 삽입 
```list[ : 0] = [100] -> [100,1,2,3,4,5]```

### list[ len(list) : ] = [ ? ] 
> 리스트 맨 마지막에 ?를 삽입 
```list [ len( list ) : ]  = [ 100 ] -> [1, 2, 3, 4, 5, 100]```

### list[a : b] = [ ?, ?] 
> a번부터b번까지의 숫자를 ?로 변경 
```list[0 : 2] = [ 44, 22] -> [44, 22, 3, 4, 5]```

### list[a : b] = [ ] 
> a부터 b-1까지의 숫자를 삭제 
```list[1 : 3] = [ ] -> [1, 4, 5]) / a를 비워놓을 경우 0```

-----------------------------------------------------------------------------

# 튜플
```
t = 1,2,3,4,5
type(t) = tuple
t [0:2] = [1,2,3]
```

/ , + ,* 등 연산은 가능하지만 리스트 삽입,삭제,치환 등은 불가능

# 튜플 메소드

```t.count( ? )``` -> t에 있는 요소중 ? 의 개수를 센다   
```sorted(t)``` -> t에 있는 요소들을 순서대로 정렬 (예 : 가나다 순)   

# 튜플 -> 리스트 로 변환

```li = list(t)``` -> t에 있던 정보가 li에 리스트로 만들어짐

# 튜플로 구구단 출력
```
dans = (2,3,4,5,6,7,8,9) #튜플
print('구구단표')
print('-' * 30)

for dan in dans : 
    for i in range(1,10):
        print('%d x %d = %d' % (dan,i,dan*i)) # ? x ? = ? 출력문
        
    print('-' * 30)
```

결과 : 구구단 출력

-----------------------------------------------------------------------------

# 딕셔너리

*리스트,튜플과 달리 인덱스가 없음

변수 = {key : value}   
변수 = {}   
변수 = dict()   

```d = {"이름" : "김마마", "수학" : 90 , "영어" : 30 , "과학" : 50}```

# 수정
```d["수학"] = 0``` -> 수학 점수가 0으로 수정됨

# 삭제
```del d["수학"]``` -> "수학" 과 수학점수가 삭제됨

# 딕셔너리 메소드

### enumerate() 
> 인덱스와 값을 다룰 때

```
for i , key in enumerate(d) :
    print (i,key,d.get(key))
```
결과   
   
0 이름 김마마   
1 수학 90   
2 영어 30   
3 과학 50   

### .values()   
> 값을 다룰때 (int나 str 형식이 아님)   
   
### .keys()   
> 키를 다룰때
   
### .get( key )   
> 입력한 key의 value를 가져옴(숫자일경우 int , 문자일경우 str)
   
### items()   
> 키와 값을 다룰 때   
   
```
for k , v in d.items() :
    print(k,v)
```
결과   
   
이름 김마마   
수학 90    
영어 30   
과학 50   

### zip()   
> 시퀀스 쌍을 만든다

### reverse()   
> 역방향 시퀀스 생성

### sorted()   
> 정렬된 결과
   
# 점수 합계와 평균 구하기

```
scores = {'김예진' : 90 , '박영진' : 95 , '김소희' : 84}

sum = 0
for key in scores :
    sum += scores[key]
    print('%s : %d' % (key,scores[key]))
    
avg = sum/len(scores)
print('합계 : %d, 평균 : %2.f' % (sum,avg))
```
결과   
   
김예진 : 90   
박영진 : 95   
김소희 : 84   
합계 : 269, 평균 : 90

-----------------------------------------------------------------------------

# 함수
```
def 함수명() :                     #함수선언
    함수내용                       #함수를 호출하면 실행되는 코드

함수명() :                         #함수호출
```
```
def 함수명(매개변수1 , 매개변수2) : #함수선언,매개변수의 개수가 정해져있음
	함수내용                   #함수를 호출하면 실행되는 코드

함수명(입력값1, 입력값2)            #함수 호출
```

```
def 함수명( *매개변수 )             #함수선언,매개변수앞에 *을 붙여 매개변수의 개수가 정해져있지않음
	함수내용
```

> 매개변수 입력값에 리스트,튜플,딕셔너리 넣을수 있음
# 매개변수의 변수 값 전달 방식
## 1. 파이썬의 값에 의한 호출
```
(서브루틴)

def func(x) :
    x = 100
    print("func() : x =", x, ",id =", id(x))

(메인루틴)

x = 10
print("func() : x =", x, ",id =", id(x))
func(x)
print("func() : x =", x, ",id =", id(x))
```
결과   
   
메인 : x = 10 ,id = 1701949920   
func() : x = 100 ,id = 1701952800   
메인 : x = 10 ,id = 1701949920   

>메인루틴의 변수값을 서브루틴(func()함수)의 매개변수 값에 "복사"하기때문에 
값이 저장되는 메모리 주소가 다르다. 즉 서로 전혀 다른 변수

## 2. 레퍼런스에 의한 호출
```
def func(x) :
    x[0] = 100
    print("func() : x =",x,",id =",id(x))
    
x = [1,2,3]
print("메인 : x =",x,", id =",id(x))
func(x)
print("메인 : x =",x,", id =",id(x))
```
결과   
    
메인 : x = [1, 2, 3] , id = 1941260756680   
func() : x = [100, 2, 3] ,id = 1941260756680   
메인 : x = [100, 2, 3] , id = 1941260756680   

> 파이썬의 리스트,튜플,딕셔너리나 c,c++의 포인터를 매개변수로 전달시에는
메인루틴의 메모리주소를 서브루틴의 매개변수에 "전달"해 수정하거나 삭제하기때문에
값이 달라져도 저장되는 메모리주소는 같다.

# 변수의 범위
## 1. 지역변수

> 지역변수는 호출 된 함수 내에서만 유효하다
호출 된 함수 내가 아닌 곳에서 같은 이름으로 변수를 선언해도
그 두 변수는 저장된 메모리주소가 다른 전혀다른 변수가 된다.

> 만약 지역변수를 전역변수로 사용하고싶다면 변수 앞에 global을 붙이면 됨

## 2. 전역변수

> 전역변수는 메인루틴에서 사용되는 변수로서 하위 모든 함수에서 유효하다.

## return A 
> A 리턴
-----------------------------------------------------------------------------

# is
> 타입으로 비교
```
a = 10
b = "hi"
a is b -> False
```
