---
layout: single
title:  "Logistic Regression Classifier Clone"

---

<head>
  <style>
    table.dataframe {
      white-space: normal;
      width: 100%;
      height: 240px;
      display: block;
      overflow: auto;
      font-family: Arial, sans-serif;
      font-size: 0.9rem;
      line-height: 20px;
      text-align: center;
      border: 0px !important;
    }

    table.dataframe th {
      text-align: center;
      font-weight: bold;
      padding: 8px;
    }

    table.dataframe td {
      text-align: center;
      padding: 8px;
    }

    table.dataframe tr:hover {
      background: #b8d1f3; 
    }

    .output_prompt {
      overflow: auto;
      font-size: 0.9rem;
      line-height: 1.45;
      border-radius: 0.3rem;
      -webkit-overflow-scrolling: touch;
      padding: 0.8rem;
      margin-top: 0;
      margin-bottom: 15px;
      font: 1rem Consolas, "Liberation Mono", Menlo, Courier, monospace;
      color: $code-text-color;
      border: solid 1px $border-color;
      border-radius: 0.3rem;
      word-break: normal;
      white-space: pre;
    }

  .dataframe tbody tr th:only-of-type {
      vertical-align: middle;
  }

  .dataframe tbody tr th {
      vertical-align: top;
  }

  .dataframe thead th {
      text-align: center !important;
      padding: 8px;
  }

  .page__content p {
      margin: 0 0 0px !important;
  }

  .page__content p > strong {
    font-size: 0.8rem !important;
  }

  </style>
</head>


<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
0
"
>
<
/
a
>


#
 
*
*
L
o
g
i
s
t
i
c
 
R
e
g
r
e
s
s
i
o
n
 
C
l
a
s
s
i
f
i
e
r
 
T
u
t
o
r
i
a
l
 
w
i
t
h
 
P
y
t
h
o
n
*
*




#
 
로
지
스
틱
 
회
귀
 
분
류
기
 
_
_
 
김
정
연


<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
0
.
1
"
>
<
/
a
>


#
 
*
*
목
차
*
*






1
.
	
[
로
지
스
틱
 
회
귀
 
소
개
]
(
#
1
)


2
.
	
[
로
지
스
틱
 
회
귀
 
직
관
]
(
#
2
)


3
.
	
[
로
지
스
틱
 
회
귀
 
분
석
의
 
가
정
]
(
#
3
)


4
.
	
[
로
지
스
틱
 
회
귀
 
분
석
 
유
형
]
(
#
4
)


5
.
	
[
I
m
p
o
r
t
 
l
i
b
r
a
r
i
e
s
]
(
#
5
)


6
.
	
[
I
m
p
o
r
t
 
d
a
t
a
s
e
t
]
(
#
6
)


7
.
	
[
데
이
터
 
분
석
 
탐
색
하
기
]
(
#
7
)


8
.
	
[
f
e
a
t
u
r
e
 
v
e
c
t
o
r
,
 
목
표
 
변
수
 
선
언
하
기
]
(
#
8
)


9
.
	
[
t
r
a
i
n
i
n
g
,
 
t
e
s
t
 
s
e
t
 
으
로
 
분
리
하
기
]
(
#
9
)


1
0
.
	
[
F
e
a
t
u
r
e
 
e
n
g
i
n
e
e
r
i
n
g
]
(
#
1
0
)


1
1
.
	
[
F
e
a
t
u
r
e
 
s
c
a
l
i
n
g
]
(
#
1
1
)


1
2
.
	
[
모
델
 
학
습
]
(
#
1
2
)


1
3
.
	
[
예
측
결
과
]
(
#
1
3
)


1
4
.
	
[
정
확
도
 
점
수
 
확
인
하
기
]
(
#
1
4
)


1
5
.
	
[
혼
동
 
행
렬
C
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
]
(
#
1
5
)


1
6
.
	
[
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
m
e
t
r
i
c
e
s
]
(
#
1
6
)


1
7
.
	
[
임
계
값
 
레
벨
 
조
정
]
(
#
1
7
)


1
8
.
	
[
R
O
C
 
-
 
A
U
C
]
(
#
1
8
)


1
9
.
	
[
k
-
F
o
l
d
 
C
r
o
s
s
 
V
a
l
i
d
a
t
i
o
n
]
(
#
1
9
)


2
0
.
	
[
H
y
p
e
r
p
a
r
a
m
e
t
e
r
 
o
p
t
i
m
i
z
a
t
i
o
n
 
u
s
i
n
g
 
G
r
i
d
S
e
a
r
c
h
 
C
V
]
(
#
2
0
)


2
1
.
	
[
결
과
와
 
결
론
]
(
#
2
1
)


2
2
.
 
[
참
조
]
(
#
2
2
)




#
 
*
*
1
.
 
로
지
스
틱
 
회
귀
 
분
석
의
 
가
정
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)






로
지
스
틱
 
회
귀
분
석
은
 
주
어
진
 
독
립
 
변
수
의
 
선
형
 
조
합
을
 
이
용
하
여
 
종
속
 
변
수
를
 
예
측
하
는
 
통
계
 
기
법
 
중
 
하
나
입
니
다
.
 
주
로
 
*
*
이
진
 
분
류
(
b
i
n
a
r
y
 
c
l
a
s
s
i
f
i
c
a
t
i
o
n
)
*
*
 
문
제
에
 
사
용
되
며
,
 
예
측
값
이
 
이
산
적
인
(
d
i
s
c
r
e
t
e
)
 
형
태
를
 
가
집
니
다
.




로
지
스
틱
 
회
귀
분
석
에
서
는
 
로
지
스
틱
 
함
수
를
 
이
용
하
여
 
종
속
 
변
수
의
 
값
을
 
0
과
 
1
사
이
로
 
제
한
합
니
다
.
 
로
지
스
틱
 
함
수
를
 
이
용
하
여
 
예
측
된
 
값
이
 
0
.
5
보
다
 
크
면
 
1
로
 
분
류
하
고
,
 
그
렇
지
 
않
으
면
 
0
으
로
 
분
류
합
니
다
.




로
지
스
틱
 
회
귀
분
석
은
 
선
형
 
회
귀
분
석
과
 
달
리
,
 
독
립
 
변
수
와
 
종
속
 
변
수
 
사
이
의
 
관
계
가
 
선
형
이
 
아
닐
 
수
도
 
있
습
니
다
.
 
이
를
 
위
해
 
로
지
스
틱
 
함
수
를
 
사
용
하
여
 
비
선
형
적
인
 
형
태
의
 
관
계
를
 
모
델
링
할
 
수
 
있
습
니
다
.




#
 
*
*
2
.
 
로
지
스
틱
 
회
귀
 
분
석
 
유
형
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
2
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)






통
계
학
에
서
 
*
*
로
지
스
틱
 
회
귀
 
모
델
(
L
o
g
i
s
t
i
c
 
R
e
g
r
e
s
s
i
o
n
 
m
o
d
e
l
)
*
*
은
 
주
로
 
분
류
 
목
적
으
로
 
사
용
되
는
 
널
리
 
사
용
되
는
 
통
계
 
모
델
입
니
다
.
 
즉
,
 
일
련
의
 
관
측
치
가
 
주
어
졌
을
 
때
,
 
로
지
스
틱
 
회
귀
 
알
고
리
즘
은
 
이
러
한
 
관
측
치
를
 
두
 
개
 
이
상
의
 
이
산
적
인
 
클
래
스
로
 
분
류
하
는
 
데
 
도
움
이
 
됩
니
다
.
 
따
라
서
 
대
상
 
변
수
는
 
이
산
적
인
 
형
태
를
 
가
집
니
다
.




로
지
스
틱
 
회
귀
 
알
고
리
즘
은
 
다
음
과
 
같
이
 
작
동
합
니
다
.


#
#
 
*
*
선
형
방
정
식
 
구
현
하
기
*
*








로
지
스
틱
 
회
귀
 
분
석
 
알
고
리
즘
은
 
반
응
 
값
을
 
예
측
하
기
 
위
해
 
독
립
 
변
수
 
또
는
 
설
명
 
변
수
가
 
있
는
 
선
형
 
방
정
식
을
 
구
현
하
는
 
방
식
으
로
 
작
동
합
니
다
.
 
예
를
 
들
어
,
 
우
리
는
 
공
부
한
 
시
간
의
 
수
와
 
시
험
에
 
합
격
할
 
확
률
의
 
예
를
 
고
려
합
니
다
.
 
여
기
서
 
연
구
된
 
시
간
 
수
는
 
설
명
 
변
수
이
며
 
x
1
로
 
표
시
됩
니
다
.
 
합
격
 
확
률
은
 
반
응
 
변
수
 
또
는
 
목
표
 
변
수
이
며
 
z
로
 
표
시
됩
니
다
.






만
약
 
우
리
가
 
하
나
의
 
설
명
 
변
수
(
x
1
)
와
 
하
나
의
 
반
응
 
변
수
(
z
)
를
 
가
지
고
 
있
다
면
,
 
선
형
 
방
정
식
은
 
다
음
과
 
같
은
 
방
정
식
으
로
 
수
학
적
으
로
 
주
어
질
 
것
입
니
다




$
$
z
 
=
 
β
0
 
+
 
β
1
x
1
$
$




여
기
서
 
계
수
 
β
0
과
 
β
1
은
 
모
형
의
 
모
수
입
니
다
.






설
명
 
변
수
가
 
여
러
 
개
인
 
경
우
,
 
위
의
 
방
정
식
은
 
다
음
과
 
같
이
 
확
장
될
 
수
 
있
습
니
다




$
$
z
 
=
 
β
0
 
+
 
β
1
x
1
 
+
 
β
2
x
2
+
…
.
+
 
β
n
x
n
$
$




여
기
서
 
계
수
 
β
0
,
 
β
1
,
 
β
2
 
및
 
β
n
은
 
모
델
의
 
매
개
변
수
입
니
다
.




따
라
서
 
예
측
 
반
응
 
값
은
 
위
의
 
방
정
식
에
 
의
해
 
주
어
지
며
 
z
로
 
표
시
됩
니
다
.


#
#
 
*
*
시
그
모
이
드
 
함
수
*
*






예
측
된
 
응
답
 
값
을
 
z
로
 
표
기
하
고
,
 
이
 
값
은
 
0
과
 
1
 
사
이
의
 
확
률
 
값
으
로
 
변
환
됩
니
다
.
 
우
리
는
 
예
측
된
 
값
을
 
확
률
 
값
으
로
 
매
핑
하
기
 
위
해
 
시
그
모
이
드
 
함
수
를
 
사
용
합
니
다
.
 
시
그
모
이
드
 
함
수
는
 
임
의
의
 
실
수
 
값
을
 
0
과
 
1
 
사
이
의
 
확
률
 
값
으
로
 
매
핑
합
니
다
.




기
계
 
학
습
에
서
 
시
그
모
이
드
 
함
수
는
 
예
측
 
값
을
 
확
률
 
값
으
로
 
매
핑
하
는
 
데
 
사
용
됩
니
다
.
 
시
그
모
이
드
 
함
수
는
 
S
 
모
양
의
 
곡
선
을
 
가
지
며
,
 
s
i
g
m
o
i
d
 
c
u
r
v
e
라
고
도
합
니
다
.




시
그
모
이
드
 
함
수
는
 
로
지
스
틱
 
함
수
의
 
특
수
한
 
경
우
입
니
다
.
 
다
음
 
수
학
 
공
식
으
로
 
표
현
됩
니
다
.




그
래
프
로
는
 
시
그
모
이
드
 
함
수
를
 
다
음
과
 
같
은
 
그
래
프
로
 
나
타
낼
 
수
 
있
습
니
다
.


#
#
#
 
S
i
g
m
o
i
d
 
F
u
n
c
t
i
o
n




!
[
S
i
g
m
o
i
d
 
F
u
n
c
t
i
o
n
]
(
h
t
t
p
s
:
/
/
m
i
r
o
.
m
e
d
i
u
m
.
c
o
m
/
m
a
x
/
9
7
0
/
1
*
X
u
7
B
5
y
9
g
p
0
i
L
5
o
o
B
j
7
L
t
W
w
.
p
n
g
)


#
#
 
*
*
의
사
결
정
 
단
*
*




시
그
모
이
드
 
함
수
는
 
0
과
 
1
 
사
이
의
 
확
률
 
값
을
 
반
환
합
니
다
.
 
이
 
확
률
 
값
은
 
"
0
"
 
또
는
 
"
1
"
인
 
이
산
적
인
 
클
래
스
에
 
매
핑
됩
니
다
.
 
이
 
확
률
 
값
을
 
이
산
적
인
 
클
래
스
(
합
격
/
불
합
격
,
 
예
/
아
니
오
,
 
참
/
거
짓
)
에
 
매
핑
하
기
 
위
해
 
우
리
는
 
임
계
값
을
 
선
택
합
니
다
.
 
이
 
임
계
값
을
 
의
사
결
정
 
경
계
(
D
e
c
i
s
i
o
n
 
b
o
u
n
d
a
r
y
)
라
고
 
합
니
다
.
 
이
 
임
계
값
 
이
상
에
서
는
 
확
률
 
값
을
 
클
래
스
 
1
로
 
매
핑
하
고
,
 
이
하
에
서
는
 
클
래
스
 
0
으
로
 
매
핑
합
니
다
.




수
학
적
으
로
는
 
다
음
과
 
같
이
 
표
현
할
 
수
 
있
습
니
다
:




$
$
p
 
≥
 
0
.
5
 
=
>
 
클
래
스
 
=
 
1
$
$




$
$
p
 
<
 
0
.
5
 
=
>
 
클
래
스
 
=
 
0
$
$




일
반
적
으
로
,
 
의
사
결
정
 
경
계
는
 
0
.
5
로
 
설
정
됩
니
다
.
 
따
라
서
,
 
확
률
 
값
이
 
0
.
8
(
>
0
.
5
)
인
 
경
우
,
 
이
 
관
측
치
를
 
클
래
스
 
1
로
 
매
핑
합
니
다
.
 
마
찬
가
지
로
,
 
확
률
 
값
이
 
0
.
2
(
<
0
.
5
)
인
 
경
우
,
 
이
 
관
측
치
를
 
클
래
스
 
0
으
로
 
매
핑
합
니
다
.
 
이
는
 
아
래
 
그
래
프
에
서
 
표
시
됩
니
다
.


!
[
D
e
c
i
s
i
o
n
 
b
o
u
n
d
a
r
y
 
i
n
 
s
i
g
m
o
i
d
 
f
u
n
c
t
i
o
n
]
(
h
t
t
p
s
:
/
/
m
l
-
c
h
e
a
t
s
h
e
e
t
.
r
e
a
d
t
h
e
d
o
c
s
.
i
o
/
e
n
/
l
a
t
e
s
t
/
_
i
m
a
g
e
s
/
l
o
g
i
s
t
i
c
_
r
e
g
r
e
s
s
i
o
n
_
s
i
g
m
o
i
d
_
w
_
t
h
r
e
s
h
o
l
d
.
p
n
g
)


#
#
 
*
*
예
측
하
기
*
*




이
제
 
로
지
스
틱
 
회
귀
에
서
의
 
시
그
모
이
드
 
함
수
와
 
의
사
결
정
 
경
계
(
D
e
c
i
s
i
o
n
 
b
o
u
n
d
a
r
y
)
에
 
대
해
 
알
게
 
되
었
습
니
다
.
 
시
그
모
이
드
 
함
수
와
 
의
사
결
정
 
경
계
(
D
e
c
i
s
i
o
n
 
b
o
u
n
d
a
r
y
)
에
 
대
한
 
지
식
을
 
활
용
하
여
 
예
측
 
함
수
를
 
작
성
할
 
수
 
있
습
니
다
.
 
로
지
스
틱
 
회
귀
에
서
의
 
예
측
 
함
수
는
 
관
측
치
가
 
양
성
(
P
o
s
i
t
i
v
e
)
,
 
Y
e
s
 
또
는
 
T
r
u
e
인
 
확
률
을
 
반
환
합
니
다
.
 
우
리
는
 
이
를
 
클
래
스
 
1
로
 
부
르
고
 
P
(
c
l
a
s
s
 
=
 
1
)
로
 
표
기
합
니
다
.
 
확
률
이
 
1
에
 
가
까
워
질
수
록
 
관
측
치
가
 
클
래
스
 
1
에
 
속
할
 
확
률
이
 
높
아
지
며
,
 
그
렇
지
 
않
으
면
 
클
래
스
 
0
에
 
속
한
다
고
 
판
단
합
니
다
.


#
 
*
*
3
.
 
로
지
스
틱
 
회
귀
 
분
석
의
 
가
정
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
3
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)




로
지
스
틱
 
회
귀
 
모
델
은
 
여
러
 
가
지
 
핵
심
 
가
정
을
 
필
요
로
 
합
니
다
.
 
이
러
한
 
가
정
은
 
다
음
과
 
같
습
니
다
:




1
.
 
로
지
스
틱
 
회
귀
 
모
델
은
 
종
속
 
변
수
가
 
이
항
,
 
다
항
 
또
는
 
서
열
형
이
어
야
 
합
니
다
.




2
.
 
관
측
치
는
 
서
로
 
독
립
적
이
어
야
 
합
니
다
.
 
따
라
서
,
 
관
측
치
는
 
반
복
 
측
정
에
서
 
나
오
면
 
안
 
됩
니
다
.




3
.
 
로
지
스
틱
 
회
귀
 
알
고
리
즘
은
 
독
립
 
변
수
들
 
사
이
에
 
다
중
공
선
성
(
m
u
l
t
i
c
o
l
l
i
n
e
a
r
i
t
y
)
이
 
적
거
나
 
없
어
야
 
합
니
다
.
 
즉
,
 
독
립
 
변
수
들
은
 
서
로
 
높
은
 
상
관
 
관
계
를
 
가
지
면
 
안
 
됩
니
다
.




4
.
 
로
지
스
틱
 
회
귀
 
모
델
은
 
독
립
 
변
수
와
 
로
그
 
오
즈
(
l
o
g
 
o
d
d
s
)
의
 
선
형
성
을
 
가
정
합
니
다
.




5
.
 
로
지
스
틱
 
회
귀
 
모
델
의
 
성
공
은
 
표
본
 
크
기
에
 
따
라
 
달
라
집
니
다
.
 
일
반
적
으
로
,
 
높
은
 
정
확
도
를
 
얻
기
 
위
해
서
는
 
큰
 
표
본
 
크
기
가
 
필
요
합
니
다
.










#
 
*
*
4
.
 
로
지
스
틱
 
회
귀
 
분
석
 
유
형
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
4
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)






로
지
스
틱
 
회
귀
 
모
델
은
 
목
표
 
변
수
 
카
테
고
리
에
 
따
라
 
세
 
가
지
 
그
룹
으
로
 
분
류
될
 
수
 
있
습
니
다
.
 
이
 
세
 
가
지
 
그
룹
은
 
다
음
과
 
같
이
 
설
명
됩
니
다
:
-




#
#
#
 
1
.
 
이
항
 
로
지
스
틱
 
회
귀


이
항
 
로
지
스
틱
 
회
귀
에
서
는
 
목
표
 
변
수
가
 
두
 
개
의
 
가
능
한
 
카
테
고
리
를
 
가
지
고
 
있
습
니
다
.
 
대
표
적
인
 
예
는
 
예
/
아
니
오
,
 
좋
음
/
나
쁨
,
 
참
/
거
짓
,
 
스
팸
/
스
팸
 
아
님
,
 
합
격
/
불
합
격
 
등
이
 
있
습
니
다
.




#
#
#
 
2
.
 
다
항
 
로
지
스
틱
 
회
귀


다
항
 
로
지
스
틱
 
회
귀
에
서
는
 
목
표
 
변
수
가
 
순
서
 
없
이
 
세
 
개
 
이
상
의
 
카
테
고
리
를
 
가
지
고
 
있
습
니
다
.
 
따
라
서
 
세
 
개
 
이
상
의
 
명
목
적
인
 
카
테
고
리
가
 
있
습
니
다
.
 
예
를
 
들
어
,
 
과
일
 
종
류
의
 
카
테
고
리
는
 
사
과
,
 
망
고
,
 
오
렌
지
 
및
 
바
나
나
 
등
이
 
있
습
니
다
.




#
#
#
 
3
.
 
순
서
형
 
로
지
스
틱
 
회
귀


순
서
형
 
로
지
스
틱
 
회
귀
에
서
는
 
목
표
 
변
수
가
 
순
서
가
 
있
는
 
세
 
개
 
이
상
의
 
카
테
고
리
를
 
가
지
고
 
있
습
니
다
.
 
따
라
서
 
카
테
고
리
 
사
이
에
 
내
재
된
 
순
서
가
 
있
습
니
다
.
 
예
를
 
들
어
,
 
학
생
 
성
적
은
 
나
쁨
,
 
평
균
,
 
좋
음
,
 
우
수
한
 
등
으
로
 
분
류
될
 
수
 
있
습
니
다
.




#
 
*
*
5
.
 
I
m
p
o
r
t
 
l
i
b
r
a
r
i
e
s
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
5
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
#
 
T
h
i
s
 
P
y
t
h
o
n
 
3
 
e
n
v
i
r
o
n
m
e
n
t
 
c
o
m
e
s
 
w
i
t
h
 
m
a
n
y
 
h
e
l
p
f
u
l
 
a
n
a
l
y
t
i
c
s
 
l
i
b
r
a
r
i
e
s
 
i
n
s
t
a
l
l
e
d

#
 
I
t
 
i
s
 
d
e
f
i
n
e
d
 
b
y
 
t
h
e
 
k
a
g
g
l
e
/
p
y
t
h
o
n
 
d
o
c
k
e
r
 
i
m
a
g
e
:
 
h
t
t
p
s
:
/
/
g
i
t
h
u
b
.
c
o
m
/
k
a
g
g
l
e
/
d
o
c
k
e
r
-
p
y
t
h
o
n

#
 
F
o
r
 
e
x
a
m
p
l
e
,
 
h
e
r
e
'
s
 
s
e
v
e
r
a
l
 
h
e
l
p
f
u
l
 
p
a
c
k
a
g
e
s
 
t
o
 
l
o
a
d
 
i
n
 


i
m
p
o
r
t
 
n
u
m
p
y
 
a
s
 
n
p
 
#
 
l
i
n
e
a
r
 
a
l
g
e
b
r
a

i
m
p
o
r
t
 
p
a
n
d
a
s
 
a
s
 
p
d
 
#
 
d
a
t
a
 
p
r
o
c
e
s
s
i
n
g
,
 
C
S
V
 
f
i
l
e
 
I
/
O
 
(
e
.
g
.
 
p
d
.
r
e
a
d
_
c
s
v
)

i
m
p
o
r
t
 
m
a
t
p
l
o
t
l
i
b
.
p
y
p
l
o
t
 
a
s
 
p
l
t
 
#
 
d
a
t
a
 
v
i
s
u
a
l
i
z
a
t
i
o
n

i
m
p
o
r
t
 
s
e
a
b
o
r
n
 
a
s
 
s
n
s
 
#
 
s
t
a
t
i
s
t
i
c
a
l
 
d
a
t
a
 
v
i
s
u
a
l
i
z
a
t
i
o
n

%
m
a
t
p
l
o
t
l
i
b
 
i
n
l
i
n
e


#
 
I
n
p
u
t
 
d
a
t
a
 
f
i
l
e
s
 
a
r
e
 
a
v
a
i
l
a
b
l
e
 
i
n
 
t
h
e
 
"
.
.
/
i
n
p
u
t
/
"
 
d
i
r
e
c
t
o
r
y
.

#
 
F
o
r
 
e
x
a
m
p
l
e
,
 
r
u
n
n
i
n
g
 
t
h
i
s
 
(
b
y
 
c
l
i
c
k
i
n
g
 
r
u
n
 
o
r
 
p
r
e
s
s
i
n
g
 
S
h
i
f
t
+
E
n
t
e
r
)
 
w
i
l
l
 
l
i
s
t
 
a
l
l
 
f
i
l
e
s
 
u
n
d
e
r
 
t
h
e
 
i
n
p
u
t
 
d
i
r
e
c
t
o
r
y


i
m
p
o
r
t
 
o
s

f
o
r
 
d
i
r
n
a
m
e
,
 
_
,
 
f
i
l
e
n
a
m
e
s
 
i
n
 
o
s
.
w
a
l
k
(
'
/
k
a
g
g
l
e
/
i
n
p
u
t
'
)
:

 
 
 
 
f
o
r
 
f
i
l
e
n
a
m
e
 
i
n
 
f
i
l
e
n
a
m
e
s
:

 
 
 
 
 
 
 
 
p
r
i
n
t
(
o
s
.
p
a
t
h
.
j
o
i
n
(
d
i
r
n
a
m
e
,
 
f
i
l
e
n
a
m
e
)
)


#
 
A
n
y
 
r
e
s
u
l
t
s
 
y
o
u
 
w
r
i
t
e
 
t
o
 
t
h
e
 
c
u
r
r
e
n
t
 
d
i
r
e
c
t
o
r
y
 
a
r
e
 
s
a
v
e
d
 
a
s
 
o
u
t
p
u
t
.

```

<pre>
/
k
a
g
g
l
e
/
i
n
p
u
t
/
w
e
a
t
h
e
r
-
d
a
t
a
s
e
t
-
r
a
t
t
l
e
-
p
a
c
k
a
g
e
/
w
e
a
t
h
e
r
A
U
S
.
c
s
v

</pre>

```python
i
m
p
o
r
t
 
w
a
r
n
i
n
g
s


w
a
r
n
i
n
g
s
.
f
i
l
t
e
r
w
a
r
n
i
n
g
s
(
'
i
g
n
o
r
e
'
)
```

#
 
*
*
6
.
 
I
m
p
o
r
t
 
d
a
t
a
s
e
t
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
6
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
d
a
t
a
 
=
 
'
/
k
a
g
g
l
e
/
i
n
p
u
t
/
w
e
a
t
h
e
r
-
d
a
t
a
s
e
t
-
r
a
t
t
l
e
-
p
a
c
k
a
g
e
/
w
e
a
t
h
e
r
A
U
S
.
c
s
v
'


d
f
 
=
 
p
d
.
r
e
a
d
_
c
s
v
(
d
a
t
a
)
```

#
 
*
*
7
.
 
데
이
터
 
분
석
 
탐
색
하
기
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
7
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)









```python
#
 
v
i
e
w
 
d
i
m
e
n
s
i
o
n
s
 
o
f
 
d
a
t
a
s
e
t


d
f
.
s
h
a
p
e
```

<pre>
(
1
4
5
4
6
0
,
 
2
3
)
</pre>
데
이
터
셋
에
는
 
1
4
2
1
9
3
개
의
 
인
스
턴
스
와
 
2
4
개
의
 
변
수
가
 
있
다
는
 
것
을
 
확
인
할
 
수
 
있
습
니
다
.



```python
#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t


d
f
.
h
e
a
d
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
D
a
t
e
 
L
o
c
a
t
i
o
n
 
 
M
i
n
T
e
m
p
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
 
\

0
 
 
2
0
0
8
-
1
2
-
0
1
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
3
.
4
 
 
 
 
 
2
2
.
9
 
 
 
 
 
 
 
0
.
6
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 

1
 
 
2
0
0
8
-
1
2
-
0
2
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
7
.
4
 
 
 
 
 
2
5
.
1
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 

2
 
 
2
0
0
8
-
1
2
-
0
3
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
2
.
9
 
 
 
 
 
2
5
.
7
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 

3
 
 
2
0
0
8
-
1
2
-
0
4
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
9
.
2
 
 
 
 
 
2
8
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 

4
 
 
2
0
0
8
-
1
2
-
0
5
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
7
.
5
 
 
 
 
 
3
2
.
3
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 


 
 
W
i
n
d
G
u
s
t
D
i
r
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
W
i
n
d
D
i
r
9
a
m
 
 
.
.
.
 
H
u
m
i
d
i
t
y
9
a
m
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
 
 
W
 
 
.
.
.
 
 
 
 
 
 
 
 
7
1
.
0
 
 
 
 
 
 
 
 
 
2
2
.
0
 
 
 

1
 
 
 
 
 
 
 
 
 
W
N
W
 
 
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
N
N
W
 
 
.
.
.
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
 
2
5
.
0
 
 
 

2
 
 
 
 
 
 
 
 
 
W
S
W
 
 
 
 
 
 
 
 
 
 
 
4
6
.
0
 
 
 
 
 
 
 
 
 
 
W
 
 
.
.
.
 
 
 
 
 
 
 
 
3
8
.
0
 
 
 
 
 
 
 
 
 
3
0
.
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
N
E
 
 
 
 
 
 
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
 
 
S
E
 
 
.
.
.
 
 
 
 
 
 
 
 
4
5
.
0
 
 
 
 
 
 
 
 
 
1
6
.
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
 
 
 
4
1
.
0
 
 
 
 
 
 
 
 
E
N
E
 
 
.
.
.
 
 
 
 
 
 
 
 
8
2
.
0
 
 
 
 
 
 
 
 
 
3
3
.
0
 
 
 


 
 
 
P
r
e
s
s
u
r
e
9
a
m
 
 
P
r
e
s
s
u
r
e
3
p
m
 
 
C
l
o
u
d
9
a
m
 
 
C
l
o
u
d
3
p
m
 
 
T
e
m
p
9
a
m
 
 
T
e
m
p
3
p
m
 
 
R
a
i
n
T
o
d
a
y
 
 
\

0
 
 
 
 
 
 
 
1
0
0
7
.
7
 
 
 
 
 
 
 
1
0
0
7
.
1
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
1
6
.
9
 
 
 
 
 
2
1
.
8
 
 
 
 
 
 
 
 
 
N
o
 
 
 

1
 
 
 
 
 
 
 
1
0
1
0
.
6
 
 
 
 
 
 
 
1
0
0
7
.
8
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
1
7
.
2
 
 
 
 
 
2
4
.
3
 
 
 
 
 
 
 
 
 
N
o
 
 
 

2
 
 
 
 
 
 
 
1
0
0
7
.
6
 
 
 
 
 
 
 
1
0
0
8
.
7
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
2
1
.
0
 
 
 
 
 
2
3
.
2
 
 
 
 
 
 
 
 
 
N
o
 
 
 

3
 
 
 
 
 
 
 
1
0
1
7
.
6
 
 
 
 
 
 
 
1
0
1
2
.
8
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
1
8
.
1
 
 
 
 
 
2
6
.
5
 
 
 
 
 
 
 
 
 
N
o
 
 
 

4
 
 
 
 
 
 
 
1
0
1
0
.
8
 
 
 
 
 
 
 
1
0
0
6
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
1
7
.
8
 
 
 
 
 
2
9
.
7
 
 
 
 
 
 
 
 
 
N
o
 
 
 


 
 
 
R
a
i
n
T
o
m
o
r
r
o
w
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 


[
5
 
r
o
w
s
 
x
 
2
3
 
c
o
l
u
m
n
s
]
</pre>

```python
c
o
l
_
n
a
m
e
s
 
=
 
d
f
.
c
o
l
u
m
n
s


c
o
l
_
n
a
m
e
s
```

<pre>
I
n
d
e
x
(
[
'
D
a
t
e
'
,
 
'
L
o
c
a
t
i
o
n
'
,
 
'
M
i
n
T
e
m
p
'
,
 
'
M
a
x
T
e
m
p
'
,
 
'
R
a
i
n
f
a
l
l
'
,
 
'
E
v
a
p
o
r
a
t
i
o
n
'
,

 
 
 
 
 
 
 
'
S
u
n
s
h
i
n
e
'
,
 
'
W
i
n
d
G
u
s
t
D
i
r
'
,
 
'
W
i
n
d
G
u
s
t
S
p
e
e
d
'
,
 
'
W
i
n
d
D
i
r
9
a
m
'
,
 
'
W
i
n
d
D
i
r
3
p
m
'
,

 
 
 
 
 
 
 
'
W
i
n
d
S
p
e
e
d
9
a
m
'
,
 
'
W
i
n
d
S
p
e
e
d
3
p
m
'
,
 
'
H
u
m
i
d
i
t
y
9
a
m
'
,
 
'
H
u
m
i
d
i
t
y
3
p
m
'
,

 
 
 
 
 
 
 
'
P
r
e
s
s
u
r
e
9
a
m
'
,
 
'
P
r
e
s
s
u
r
e
3
p
m
'
,
 
'
C
l
o
u
d
9
a
m
'
,
 
'
C
l
o
u
d
3
p
m
'
,
 
'
T
e
m
p
9
a
m
'
,

 
 
 
 
 
 
 
'
T
e
m
p
3
p
m
'
,
 
'
R
a
i
n
T
o
d
a
y
'
,
 
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
,

 
 
 
 
 
 
d
t
y
p
e
=
'
o
b
j
e
c
t
'
)
</pre>

```python
#
 
v
i
e
w
 
s
u
m
m
a
r
y
 
o
f
 
d
a
t
a
s
e
t


d
f
.
i
n
f
o
(
)
```

<pre>
<
c
l
a
s
s
 
'
p
a
n
d
a
s
.
c
o
r
e
.
f
r
a
m
e
.
D
a
t
a
F
r
a
m
e
'
>

R
a
n
g
e
I
n
d
e
x
:
 
1
4
5
4
6
0
 
e
n
t
r
i
e
s
,
 
0
 
t
o
 
1
4
5
4
5
9

D
a
t
a
 
c
o
l
u
m
n
s
 
(
t
o
t
a
l
 
2
3
 
c
o
l
u
m
n
s
)
:

D
a
t
e
 
 
 
 
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
1
4
3
9
7
5
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
1
4
4
1
9
9
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
1
4
2
1
9
9
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
8
2
6
7
0
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
7
5
6
2
5
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
 
1
3
5
1
3
4
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
1
3
5
1
9
7
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
 
1
3
4
8
9
4
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
1
4
1
2
3
2
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
1
4
3
6
9
3
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
1
4
2
3
9
8
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
1
4
2
8
0
6
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
1
4
0
9
5
3
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
1
3
0
3
9
5
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
1
3
0
4
3
2
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
8
9
5
7
2
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
8
6
1
0
2
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
1
4
3
6
9
3
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
1
4
1
8
5
1
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
1
4
2
1
9
9
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

R
a
i
n
T
o
m
o
r
r
o
w
 
 
 
 
 
1
4
2
1
9
3
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

d
t
y
p
e
s
:
 
f
l
o
a
t
6
4
(
1
6
)
,
 
o
b
j
e
c
t
(
7
)

m
e
m
o
r
y
 
u
s
a
g
e
:
 
2
5
.
5
+
 
M
B

</pre>
#
#
#
 
변
수
 
유
형


이
번
 
섹
션
에
서
는
 
데
이
터
셋
을
 
범
주
형
 
변
수
와
 
수
치
형
 
변
수
로
 
분
류
합
니
다
.
 
데
이
터
셋
에
는
 
범
주
형
 
변
수
와
 
수
치
형
 
변
수
가
 
혼
합
되
어
 
있
습
니
다
.
 
범
주
형
 
변
수
는
 
o
b
j
e
c
t
 
데
이
터
 
타
입
을
 
가
지
고
 
있
고
,
 
수
치
형
 
변
수
는
 
f
l
o
a
t
6
4
 
데
이
터
 
타
입
을
 
가
지
고
 
있
습
니
다
.




먼
저
,
 
범
주
형
 
변
수
를
 
찾
아
보
겠
습
니
다
.



```python
#
 
f
i
n
d
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


c
a
t
e
g
o
r
i
c
a
l
 
=
 
[
v
a
r
 
f
o
r
 
v
a
r
 
i
n
 
d
f
.
c
o
l
u
m
n
s
 
i
f
 
d
f
[
v
a
r
]
.
d
t
y
p
e
=
=
'
O
'
]


p
r
i
n
t
(
'
범
주
형
 
변
수
 
개
수
 
{
}
\
n
'
.
f
o
r
m
a
t
(
l
e
n
(
c
a
t
e
g
o
r
i
c
a
l
)
)
)


p
r
i
n
t
(
'
범
주
형
 
변
수
들
은
 
다
음
과
 
같
다
 
:
'
,
 
c
a
t
e
g
o
r
i
c
a
l
)
```

<pre>
범
주
형
 
변
수
 
개
수
 
7


범
주
형
 
변
수
들
은
 
다
음
과
 
같
다
 
:
 
[
'
D
a
t
e
'
,
 
'
L
o
c
a
t
i
o
n
'
,
 
'
W
i
n
d
G
u
s
t
D
i
r
'
,
 
'
W
i
n
d
D
i
r
9
a
m
'
,
 
'
W
i
n
d
D
i
r
3
p
m
'
,
 
'
R
a
i
n
T
o
d
a
y
'
,
 
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]

</pre>

```python
#
 
v
i
e
w
 
t
h
e
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


d
f
[
c
a
t
e
g
o
r
i
c
a
l
]
.
h
e
a
d
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
D
a
t
e
 
L
o
c
a
t
i
o
n
 
W
i
n
d
G
u
s
t
D
i
r
 
W
i
n
d
D
i
r
9
a
m
 
W
i
n
d
D
i
r
3
p
m
 
R
a
i
n
T
o
d
a
y
 
 
\

0
 
 
2
0
0
8
-
1
2
-
0
1
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
W
N
W
 
 
 
 
 
 
 
 
N
o
 
 
 

1
 
 
2
0
0
8
-
1
2
-
0
2
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
W
N
W
 
 
 
 
 
 
 
 
N
N
W
 
 
 
 
 
 
 
 
W
S
W
 
 
 
 
 
 
 
 
N
o
 
 
 

2
 
 
2
0
0
8
-
1
2
-
0
3
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
W
S
W
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
W
S
W
 
 
 
 
 
 
 
 
N
o
 
 
 

3
 
 
2
0
0
8
-
1
2
-
0
4
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
N
E
 
 
 
 
 
 
 
 
 
S
E
 
 
 
 
 
 
 
 
 
 
E
 
 
 
 
 
 
 
 
N
o
 
 
 

4
 
 
2
0
0
8
-
1
2
-
0
5
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
E
N
E
 
 
 
 
 
 
 
 
 
N
W
 
 
 
 
 
 
 
 
N
o
 
 
 


 
 
R
a
i
n
T
o
m
o
r
r
o
w
 
 

0
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

1
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

2
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

3
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 

4
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 
</pre>
#
#
#
 
범
주
형
 
변
수
 
요
약


`
D
a
t
e
`
 
변
수
가
 
있
습
니
다
.




총
 
6
개
의
 
범
주
형
 
변
수
가
 
있
습
니
다
.
 
이
는
 
`
L
o
c
a
t
i
o
n
,
 
W
i
n
d
G
u
s
t
D
i
r
,
 
W
i
n
d
D
i
r
9
a
m
,
 
W
i
n
d
D
i
r
3
p
m
,
 
R
a
i
n
T
o
d
a
y
,
 
R
a
i
n
T
o
m
o
r
r
o
w
`
 
입
니
다
.




이
 
중
 
`
R
a
i
n
T
o
d
a
y
`
와
 
`
R
a
i
n
T
o
m
o
r
r
o
w
`
 
변
수
는
 
이
진
 
범
주
형
 
변
수
입
니
다
.




`
R
a
i
n
T
o
m
o
r
r
o
w
`
 
변
수
는
 
타
겟
 
변
수
입
니
다
.


#
#
 
범
주
형
 
변
수
 
내
 
문
제
 
탐
구


첫
째
로
,
 
범
주
형
 
변
수
를
 
살
펴
보
겠
습
니
다
.




#
#
#
 
범
주
형
 
변
수
 
내
 
결
측
치



```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


d
f
[
c
a
t
e
g
o
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
D
a
t
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
1
0
3
2
6

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
1
0
5
6
6

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
4
2
2
8

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
3
2
6
1

R
a
i
n
T
o
m
o
r
r
o
w
 
 
 
 
 
3
2
6
7

d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
p
r
i
n
t
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
c
o
n
t
a
i
n
i
n
g
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s


c
a
t
1
 
=
 
[
v
a
r
 
f
o
r
 
v
a
r
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
i
f
 
d
f
[
v
a
r
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
!
=
0
]


p
r
i
n
t
(
d
f
[
c
a
t
1
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
)
```

<pre>
W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
1
0
3
2
6

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
1
0
5
6
6

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
4
2
2
8

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
3
2
6
1

R
a
i
n
T
o
m
o
r
r
o
w
 
 
 
 
 
3
2
6
7

d
t
y
p
e
:
 
i
n
t
6
4

</pre>
데
이
터
 
세
트
에
는
 
결
측
값
이
 
있
는
 
범
주
형
 
변
수
가
 
4
개
만
 
있
습
니
다
.
 
이
것
들
은
 
`
W
i
n
d
G
u
s
t
D
i
r
,
 
W
i
n
d
D
i
r
9
a
m
,
 
W
i
n
d
D
i
r
3
p
m
,
 
R
a
i
n
T
o
d
a
y
`
입
니
다
.


#
#
#
 
범
주
형
 
변
수
의
 
빈
도
수
 
카
운
트


이
제
 
범
주
형
 
변
수
의
 
빈
도
수
 
카
운
트
를
 
확
인
해
보
겠
습
니
다
.



```python
#
 
v
i
e
w
 
f
r
e
q
u
e
n
c
y
 
o
f
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


f
o
r
 
v
a
r
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
:
 

 
 
 
 

 
 
 
 
p
r
i
n
t
(
d
f
[
v
a
r
]
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
)
```

<pre>
2
0
1
3
-
0
8
-
2
8
 
 
 
 
4
9

2
0
1
6
-
0
1
-
0
8
 
 
 
 
4
9

2
0
1
6
-
1
1
-
1
5
 
 
 
 
4
9

2
0
1
7
-
0
4
-
0
2
 
 
 
 
4
9

2
0
1
4
-
1
0
-
2
3
 
 
 
 
4
9

 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.

2
0
0
7
-
1
1
-
0
2
 
 
 
 
 
1

2
0
0
7
-
1
1
-
1
2
 
 
 
 
 
1

2
0
0
7
-
1
2
-
1
6
 
 
 
 
 
1

2
0
0
8
-
0
1
-
2
5
 
 
 
 
 
1

2
0
0
7
-
1
1
-
0
5
 
 
 
 
 
1

N
a
m
e
:
 
D
a
t
e
,
 
L
e
n
g
t
h
:
 
3
4
3
6
,
 
d
t
y
p
e
:
 
i
n
t
6
4

C
a
n
b
e
r
r
a
 
 
 
 
 
 
 
 
 
 
 
 
3
4
3
6

S
y
d
n
e
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
3
4
4

H
o
b
a
r
t
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

D
a
r
w
i
n
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

B
r
i
s
b
a
n
e
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

P
e
r
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

A
d
e
l
a
i
d
e
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

M
e
l
b
o
u
r
n
e
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

A
l
b
a
n
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

M
o
u
n
t
G
i
n
i
n
i
 
 
 
 
 
 
 
 
 
3
0
4
0

T
o
w
n
s
v
i
l
l
e
 
 
 
 
 
 
 
 
 
 
3
0
4
0

M
o
u
n
t
G
a
m
b
i
e
r
 
 
 
 
 
 
 
 
3
0
4
0

G
o
l
d
C
o
a
s
t
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

L
a
u
n
c
e
s
t
o
n
 
 
 
 
 
 
 
 
 
 
3
0
4
0

A
l
i
c
e
S
p
r
i
n
g
s
 
 
 
 
 
 
 
 
3
0
4
0

B
a
l
l
a
r
a
t
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

W
o
l
l
o
n
g
o
n
g
 
 
 
 
 
 
 
 
 
 
3
0
4
0

C
a
i
r
n
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

B
e
n
d
i
g
o
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

N
e
w
c
a
s
t
l
e
 
 
 
 
 
 
 
 
 
 
 
3
0
3
9

T
u
g
g
e
r
a
n
o
n
g
 
 
 
 
 
 
 
 
 
3
0
3
9

P
e
n
r
i
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
3
9

N
u
r
i
o
o
t
p
a
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

P
o
r
t
l
a
n
d
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

M
o
r
e
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

M
i
l
d
u
r
a
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

N
o
r
f
o
l
k
I
s
l
a
n
d
 
 
 
 
 
 
 
3
0
0
9

R
i
c
h
m
o
n
d
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

M
e
l
b
o
u
r
n
e
A
i
r
p
o
r
t
 
 
 
 
3
0
0
9

W
o
o
m
e
r
a
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

C
o
b
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

W
a
t
s
o
n
i
a
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

W
a
g
g
a
W
a
g
g
a
 
 
 
 
 
 
 
 
 
 
3
0
0
9

P
e
r
t
h
A
i
r
p
o
r
t
 
 
 
 
 
 
 
 
3
0
0
9

B
a
d
g
e
r
y
s
C
r
e
e
k
 
 
 
 
 
 
 
3
0
0
9

S
y
d
n
e
y
A
i
r
p
o
r
t
 
 
 
 
 
 
 
3
0
0
9

P
e
a
r
c
e
R
A
A
F
 
 
 
 
 
 
 
 
 
 
3
0
0
9

C
o
f
f
s
H
a
r
b
o
u
r
 
 
 
 
 
 
 
 
3
0
0
9

W
i
t
c
h
c
l
i
f
f
e
 
 
 
 
 
 
 
 
 
3
0
0
9

S
a
l
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

D
a
r
t
m
o
o
r
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

W
i
l
l
i
a
m
t
o
w
n
 
 
 
 
 
 
 
 
 
3
0
0
9

W
a
l
p
o
l
e
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
6

N
o
r
a
h
H
e
a
d
 
 
 
 
 
 
 
 
 
 
 
3
0
0
4

S
a
l
m
o
n
G
u
m
s
 
 
 
 
 
 
 
 
 
 
3
0
0
1

N
h
i
l
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
5
7
8

U
l
u
r
u
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
5
7
8

K
a
t
h
e
r
i
n
e
 
 
 
 
 
 
 
 
 
 
 
1
5
7
8

N
a
m
e
:
 
L
o
c
a
t
i
o
n
,
 
d
t
y
p
e
:
 
i
n
t
6
4

W
 
 
 
 
 
 
9
9
1
5

S
E
 
 
 
 
 
9
4
1
8

N
 
 
 
 
 
 
9
3
1
3

S
S
E
 
 
 
 
9
2
1
6

E
 
 
 
 
 
 
9
1
8
1

S
 
 
 
 
 
 
9
1
6
8

W
S
W
 
 
 
 
9
0
6
9

S
W
 
 
 
 
 
8
9
6
7

S
S
W
 
 
 
 
8
7
3
6

W
N
W
 
 
 
 
8
2
5
2

N
W
 
 
 
 
 
8
1
2
2

E
N
E
 
 
 
 
8
1
0
4

E
S
E
 
 
 
 
7
3
7
2

N
E
 
 
 
 
 
7
1
3
3

N
N
W
 
 
 
 
6
6
2
0

N
N
E
 
 
 
 
6
5
4
8

N
a
m
e
:
 
W
i
n
d
G
u
s
t
D
i
r
,
 
d
t
y
p
e
:
 
i
n
t
6
4

N
 
 
 
 
 
 
1
1
7
5
8

S
E
 
 
 
 
 
 
9
2
8
7

E
 
 
 
 
 
 
 
9
1
7
6

S
S
E
 
 
 
 
 
9
1
1
2

N
W
 
 
 
 
 
 
8
7
4
9

S
 
 
 
 
 
 
 
8
6
5
9

W
 
 
 
 
 
 
 
8
4
5
9

S
W
 
 
 
 
 
 
8
4
2
3

N
N
E
 
 
 
 
 
8
1
2
9

N
N
W
 
 
 
 
 
7
9
8
0

E
N
E
 
 
 
 
 
7
8
3
6

N
E
 
 
 
 
 
 
7
6
7
1

E
S
E
 
 
 
 
 
7
6
3
0

S
S
W
 
 
 
 
 
7
5
8
7

W
N
W
 
 
 
 
 
7
4
1
4

W
S
W
 
 
 
 
 
7
0
2
4

N
a
m
e
:
 
W
i
n
d
D
i
r
9
a
m
,
 
d
t
y
p
e
:
 
i
n
t
6
4

S
E
 
 
 
 
 
1
0
8
3
8

W
 
 
 
 
 
 
1
0
1
1
0

S
 
 
 
 
 
 
 
9
9
2
6

W
S
W
 
 
 
 
 
9
5
1
8

S
S
E
 
 
 
 
 
9
3
9
9

S
W
 
 
 
 
 
 
9
3
5
4

N
 
 
 
 
 
 
 
8
8
9
0

W
N
W
 
 
 
 
 
8
8
7
4

N
W
 
 
 
 
 
 
8
6
1
0

E
S
E
 
 
 
 
 
8
5
0
5

E
 
 
 
 
 
 
 
8
4
7
2

N
E
 
 
 
 
 
 
8
2
6
3

S
S
W
 
 
 
 
 
8
1
5
6

N
N
W
 
 
 
 
 
7
8
7
0

E
N
E
 
 
 
 
 
7
8
5
7

N
N
E
 
 
 
 
 
6
5
9
0

N
a
m
e
:
 
W
i
n
d
D
i
r
3
p
m
,
 
d
t
y
p
e
:
 
i
n
t
6
4

N
o
 
 
 
 
 
1
1
0
3
1
9

Y
e
s
 
 
 
 
 
3
1
8
8
0

N
a
m
e
:
 
R
a
i
n
T
o
d
a
y
,
 
d
t
y
p
e
:
 
i
n
t
6
4

N
o
 
 
 
 
 
1
1
0
3
1
6

Y
e
s
 
 
 
 
 
3
1
8
7
7

N
a
m
e
:
 
R
a
i
n
T
o
m
o
r
r
o
w
,
 
d
t
y
p
e
:
 
i
n
t
6
4

</pre>

```python
#
 
v
i
e
w
 
f
r
e
q
u
e
n
c
y
 
d
i
s
t
r
i
b
u
t
i
o
n
 
o
f
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


f
o
r
 
v
a
r
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
:
 

 
 
 
 

 
 
 
 
p
r
i
n
t
(
d
f
[
v
a
r
]
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
/
n
p
.
f
l
o
a
t
(
l
e
n
(
d
f
)
)
)
```

<pre>
2
0
1
3
-
0
8
-
2
8
 
 
 
 
0
.
0
0
0
3
3
7

2
0
1
6
-
0
1
-
0
8
 
 
 
 
0
.
0
0
0
3
3
7

2
0
1
6
-
1
1
-
1
5
 
 
 
 
0
.
0
0
0
3
3
7

2
0
1
7
-
0
4
-
0
2
 
 
 
 
0
.
0
0
0
3
3
7

2
0
1
4
-
1
0
-
2
3
 
 
 
 
0
.
0
0
0
3
3
7

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

2
0
0
7
-
1
1
-
0
2
 
 
 
 
0
.
0
0
0
0
0
7

2
0
0
7
-
1
1
-
1
2
 
 
 
 
0
.
0
0
0
0
0
7

2
0
0
7
-
1
2
-
1
6
 
 
 
 
0
.
0
0
0
0
0
7

2
0
0
8
-
0
1
-
2
5
 
 
 
 
0
.
0
0
0
0
0
7

2
0
0
7
-
1
1
-
0
5
 
 
 
 
0
.
0
0
0
0
0
7

N
a
m
e
:
 
D
a
t
e
,
 
L
e
n
g
t
h
:
 
3
4
3
6
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

C
a
n
b
e
r
r
a
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
3
6
2
2

S
y
d
n
e
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
2
9
8
9

H
o
b
a
r
t
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
9
5
1

D
a
r
w
i
n
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
9
5
1

B
r
i
s
b
a
n
e
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
9
5
1

P
e
r
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
9
5
1

A
d
e
l
a
i
d
e
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
9
5
1

M
e
l
b
o
u
r
n
e
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
9
5
1

A
l
b
a
n
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

M
o
u
n
t
G
i
n
i
n
i
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

T
o
w
n
s
v
i
l
l
e
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

M
o
u
n
t
G
a
m
b
i
e
r
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

G
o
l
d
C
o
a
s
t
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

L
a
u
n
c
e
s
t
o
n
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

A
l
i
c
e
S
p
r
i
n
g
s
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

B
a
l
l
a
r
a
t
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

W
o
l
l
o
n
g
o
n
g
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

C
a
i
r
n
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

B
e
n
d
i
g
o
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
9

N
e
w
c
a
s
t
l
e
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
2

T
u
g
g
e
r
a
n
o
n
g
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
2

P
e
n
r
i
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
8
9
2

N
u
r
i
o
o
t
p
a
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

P
o
r
t
l
a
n
d
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

M
o
r
e
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

M
i
l
d
u
r
a
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

N
o
r
f
o
l
k
I
s
l
a
n
d
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

R
i
c
h
m
o
n
d
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

M
e
l
b
o
u
r
n
e
A
i
r
p
o
r
t
 
 
 
 
0
.
0
2
0
6
8
6

W
o
o
m
e
r
a
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

C
o
b
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

W
a
t
s
o
n
i
a
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

W
a
g
g
a
W
a
g
g
a
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

P
e
r
t
h
A
i
r
p
o
r
t
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

B
a
d
g
e
r
y
s
C
r
e
e
k
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

S
y
d
n
e
y
A
i
r
p
o
r
t
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

P
e
a
r
c
e
R
A
A
F
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

C
o
f
f
s
H
a
r
b
o
u
r
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

W
i
t
c
h
c
l
i
f
f
e
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

S
a
l
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

D
a
r
t
m
o
o
r
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

W
i
l
l
i
a
m
t
o
w
n
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
8
6

W
a
l
p
o
l
e
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
6
5

N
o
r
a
h
H
e
a
d
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
5
2

S
a
l
m
o
n
G
u
m
s
 
 
 
 
 
 
 
 
 
 
0
.
0
2
0
6
3
1

N
h
i
l
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
1
0
8
4
8

U
l
u
r
u
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
1
0
8
4
8

K
a
t
h
e
r
i
n
e
 
 
 
 
 
 
 
 
 
 
 
0
.
0
1
0
8
4
8

N
a
m
e
:
 
L
o
c
a
t
i
o
n
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

W
 
 
 
 
 
 
0
.
0
6
8
1
6
3

S
E
 
 
 
 
 
0
.
0
6
4
7
4
6

N
 
 
 
 
 
 
0
.
0
6
4
0
2
4

S
S
E
 
 
 
 
0
.
0
6
3
3
5
8

E
 
 
 
 
 
 
0
.
0
6
3
1
1
7

S
 
 
 
 
 
 
0
.
0
6
3
0
2
8

W
S
W
 
 
 
 
0
.
0
6
2
3
4
7

S
W
 
 
 
 
 
0
.
0
6
1
6
4
6

S
S
W
 
 
 
 
0
.
0
6
0
0
5
8

W
N
W
 
 
 
 
0
.
0
5
6
7
3
0

N
W
 
 
 
 
 
0
.
0
5
5
8
3
7

E
N
E
 
 
 
 
0
.
0
5
5
7
1
3

E
S
E
 
 
 
 
0
.
0
5
0
6
8
1

N
E
 
 
 
 
 
0
.
0
4
9
0
3
8

N
N
W
 
 
 
 
0
.
0
4
5
5
1
1

N
N
E
 
 
 
 
0
.
0
4
5
0
1
6

N
a
m
e
:
 
W
i
n
d
G
u
s
t
D
i
r
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

N
 
 
 
 
 
 
0
.
0
8
0
8
3
3

S
E
 
 
 
 
 
0
.
0
6
3
8
4
6

E
 
 
 
 
 
 
0
.
0
6
3
0
8
3

S
S
E
 
 
 
 
0
.
0
6
2
6
4
3

N
W
 
 
 
 
 
0
.
0
6
0
1
4
7

S
 
 
 
 
 
 
0
.
0
5
9
5
2
8

W
 
 
 
 
 
 
0
.
0
5
8
1
5
3

S
W
 
 
 
 
 
0
.
0
5
7
9
0
6

N
N
E
 
 
 
 
0
.
0
5
5
8
8
5

N
N
W
 
 
 
 
0
.
0
5
4
8
6
0

E
N
E
 
 
 
 
0
.
0
5
3
8
7
0

N
E
 
 
 
 
 
0
.
0
5
2
7
3
6

E
S
E
 
 
 
 
0
.
0
5
2
4
5
4

S
S
W
 
 
 
 
0
.
0
5
2
1
5
9

W
N
W
 
 
 
 
0
.
0
5
0
9
6
9

W
S
W
 
 
 
 
0
.
0
4
8
2
8
8

N
a
m
e
:
 
W
i
n
d
D
i
r
9
a
m
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

S
E
 
 
 
 
 
0
.
0
7
4
5
0
8

W
 
 
 
 
 
 
0
.
0
6
9
5
0
4

S
 
 
 
 
 
 
0
.
0
6
8
2
3
9

W
S
W
 
 
 
 
0
.
0
6
5
4
3
4

S
S
E
 
 
 
 
0
.
0
6
4
6
1
6

S
W
 
 
 
 
 
0
.
0
6
4
3
0
6

N
 
 
 
 
 
 
0
.
0
6
1
1
1
6

W
N
W
 
 
 
 
0
.
0
6
1
0
0
6

N
W
 
 
 
 
 
0
.
0
5
9
1
9
2

E
S
E
 
 
 
 
0
.
0
5
8
4
7
0

E
 
 
 
 
 
 
0
.
0
5
8
2
4
3

N
E
 
 
 
 
 
0
.
0
5
6
8
0
6

S
S
W
 
 
 
 
0
.
0
5
6
0
7
0

N
N
W
 
 
 
 
0
.
0
5
4
1
0
4

E
N
E
 
 
 
 
0
.
0
5
4
0
1
5

N
N
E
 
 
 
 
0
.
0
4
5
3
0
5

N
a
m
e
:
 
W
i
n
d
D
i
r
3
p
m
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

N
o
 
 
 
 
 
0
.
7
5
8
4
1
5

Y
e
s
 
 
 
 
0
.
2
1
9
1
6
7

N
a
m
e
:
 
R
a
i
n
T
o
d
a
y
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

N
o
 
 
 
 
 
0
.
7
5
8
3
9
4

Y
e
s
 
 
 
 
0
.
2
1
9
1
4
6

N
a
m
e
:
 
R
a
i
n
T
o
m
o
r
r
o
w
,
 
d
t
y
p
e
:
 
f
l
o
a
t
6
4

</pre>
#
#
#
 
레
이
블
 
수
:
 
카
디
널
리
티


카
테
고
리
 
변
수
 
내
의
 
레
이
블
 
수
를
 
카
디
널
리
티
라
고
 
합
니
다
.
 
변
수
 
내
의
 
레
이
블
 
수
가
 
많
을
 
경
우
 
*
*
고
 
카
디
널
리
티
(
h
i
g
h
 
c
a
r
d
i
n
a
l
i
t
y
)
*
*
로
 
알
려
져
 
있
습
니
다
.
 
고
 
카
디
널
리
티
는
 
머
신
 
러
닝
 
모
델
에
서
 
심
각
한
 
문
제
를
 
일
으
킬
 
수
 
있
습
니
다
.
 
따
라
서
 
고
 
카
디
널
리
티
를
 
확
인
하
겠
습
니
다
.



```python
#
 
c
h
e
c
k
 
f
o
r
 
c
a
r
d
i
n
a
l
i
t
y
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


f
o
r
 
v
a
r
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
:

 
 
 
 

 
 
 
 
p
r
i
n
t
(
v
a
r
,
 
'
 
c
o
n
t
a
i
n
s
 
'
,
 
l
e
n
(
d
f
[
v
a
r
]
.
u
n
i
q
u
e
(
)
)
,
 
'
 
l
a
b
e
l
s
'
)
```

<pre>
D
a
t
e
 
 
c
o
n
t
a
i
n
s
 
 
3
4
3
6
 
 
l
a
b
e
l
s

L
o
c
a
t
i
o
n
 
 
c
o
n
t
a
i
n
s
 
 
4
9
 
 
l
a
b
e
l
s

W
i
n
d
G
u
s
t
D
i
r
 
 
c
o
n
t
a
i
n
s
 
 
1
7
 
 
l
a
b
e
l
s

W
i
n
d
D
i
r
9
a
m
 
 
c
o
n
t
a
i
n
s
 
 
1
7
 
 
l
a
b
e
l
s

W
i
n
d
D
i
r
3
p
m
 
 
c
o
n
t
a
i
n
s
 
 
1
7
 
 
l
a
b
e
l
s

R
a
i
n
T
o
d
a
y
 
 
c
o
n
t
a
i
n
s
 
 
3
 
 
l
a
b
e
l
s

R
a
i
n
T
o
m
o
r
r
o
w
 
 
c
o
n
t
a
i
n
s
 
 
3
 
 
l
a
b
e
l
s

</pre>
날
짜
 
변
수
 
D
a
t
e
가
 
전
처
리
되
어
야
 
하
는
 
것
으
로
 
나
타
납
니
다
.
 
다
음
 
섹
션
에
서
 
전
처
리
를
 
수
행
하
겠
습
니
다
.




다
른
 
모
든
 
변
수
는
 
상
대
적
으
로
 
적
은
 
수
의
 
변
수
를
 
포
함
합
니
다
.


#
#
#
 
F
e
a
t
u
r
e
 
E
n
g
i
n
e
e
r
i
n
g
 
o
f
 
D
a
t
e
 
V
a
r
i
a
b
l
e



```python
d
f
[
'
D
a
t
e
'
]
.
d
t
y
p
e
s
```

<pre>
d
t
y
p
e
(
'
O
'
)
</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
 
d
a
t
a
 
t
y
p
e
 
o
f
 
`
D
a
t
e
`
 
v
a
r
i
a
b
l
e
 
i
s
 
o
b
j
e
c
t
.
 
I
 
w
i
l
l
 
p
a
r
s
e
 
t
h
e
 
d
a
t
e
 
c
u
r
r
e
n
t
l
y
 
c
o
d
e
d
 
a
s
 
o
b
j
e
c
t
 
i
n
t
o
 
d
a
t
e
t
i
m
e
 
f
o
r
m
a
t
.



```python
#
 
p
a
r
s
e
 
t
h
e
 
d
a
t
e
s
,
 
c
u
r
r
e
n
t
l
y
 
c
o
d
e
d
 
a
s
 
s
t
r
i
n
g
s
,
 
i
n
t
o
 
d
a
t
e
t
i
m
e
 
f
o
r
m
a
t


d
f
[
'
D
a
t
e
'
]
 
=
 
p
d
.
t
o
_
d
a
t
e
t
i
m
e
(
d
f
[
'
D
a
t
e
'
]
)
```


```python
#
 
e
x
t
r
a
c
t
 
y
e
a
r
 
f
r
o
m
 
d
a
t
e


d
f
[
'
Y
e
a
r
'
]
 
=
 
d
f
[
'
D
a
t
e
'
]
.
d
t
.
y
e
a
r


d
f
[
'
Y
e
a
r
'
]
.
h
e
a
d
(
)
```

<pre>
0
 
 
 
 
2
0
0
8

1
 
 
 
 
2
0
0
8

2
 
 
 
 
2
0
0
8

3
 
 
 
 
2
0
0
8

4
 
 
 
 
2
0
0
8

N
a
m
e
:
 
Y
e
a
r
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
e
x
t
r
a
c
t
 
m
o
n
t
h
 
f
r
o
m
 
d
a
t
e


d
f
[
'
M
o
n
t
h
'
]
 
=
 
d
f
[
'
D
a
t
e
'
]
.
d
t
.
m
o
n
t
h


d
f
[
'
M
o
n
t
h
'
]
.
h
e
a
d
(
)
```

<pre>
0
 
 
 
 
1
2

1
 
 
 
 
1
2

2
 
 
 
 
1
2

3
 
 
 
 
1
2

4
 
 
 
 
1
2

N
a
m
e
:
 
M
o
n
t
h
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
e
x
t
r
a
c
t
 
d
a
y
 
f
r
o
m
 
d
a
t
e


d
f
[
'
D
a
y
'
]
 
=
 
d
f
[
'
D
a
t
e
'
]
.
d
t
.
d
a
y


d
f
[
'
D
a
y
'
]
.
h
e
a
d
(
)
```

<pre>
0
 
 
 
 
1

1
 
 
 
 
2

2
 
 
 
 
3

3
 
 
 
 
4

4
 
 
 
 
5

N
a
m
e
:
 
D
a
y
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
a
g
a
i
n
 
v
i
e
w
 
t
h
e
 
s
u
m
m
a
r
y
 
o
f
 
d
a
t
a
s
e
t


d
f
.
i
n
f
o
(
)
```

<pre>
<
c
l
a
s
s
 
'
p
a
n
d
a
s
.
c
o
r
e
.
f
r
a
m
e
.
D
a
t
a
F
r
a
m
e
'
>

R
a
n
g
e
I
n
d
e
x
:
 
1
4
5
4
6
0
 
e
n
t
r
i
e
s
,
 
0
 
t
o
 
1
4
5
4
5
9

D
a
t
a
 
c
o
l
u
m
n
s
 
(
t
o
t
a
l
 
2
6
 
c
o
l
u
m
n
s
)
:

D
a
t
e
 
 
 
 
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
d
a
t
e
t
i
m
e
6
4
[
n
s
]

L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
1
4
3
9
7
5
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
1
4
4
1
9
9
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
1
4
2
1
9
9
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
8
2
6
7
0
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
7
5
6
2
5
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
 
1
3
5
1
3
4
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
1
3
5
1
9
7
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
 
1
3
4
8
9
4
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
1
4
1
2
3
2
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
1
4
3
6
9
3
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
1
4
2
3
9
8
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
1
4
2
8
0
6
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
1
4
0
9
5
3
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
1
3
0
3
9
5
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
1
3
0
4
3
2
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
8
9
5
7
2
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
8
6
1
0
2
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
1
4
3
6
9
3
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
1
4
1
8
5
1
 
n
o
n
-
n
u
l
l
 
f
l
o
a
t
6
4

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
1
4
2
1
9
9
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

R
a
i
n
T
o
m
o
r
r
o
w
 
 
 
 
 
1
4
2
1
9
3
 
n
o
n
-
n
u
l
l
 
o
b
j
e
c
t

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
i
n
t
6
4

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
i
n
t
6
4

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
4
5
4
6
0
 
n
o
n
-
n
u
l
l
 
i
n
t
6
4

d
t
y
p
e
s
:
 
d
a
t
e
t
i
m
e
6
4
[
n
s
]
(
1
)
,
 
f
l
o
a
t
6
4
(
1
6
)
,
 
i
n
t
6
4
(
3
)
,
 
o
b
j
e
c
t
(
6
)

m
e
m
o
r
y
 
u
s
a
g
e
:
 
2
8
.
9
+
 
M
B

</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
r
e
 
a
r
e
 
t
h
r
e
e
 
a
d
d
i
t
i
o
n
a
l
 
c
o
l
u
m
n
s
 
c
r
e
a
t
e
d
 
f
r
o
m
 
`
D
a
t
e
`
 
v
a
r
i
a
b
l
e
.
 
N
o
w
,
 
I
 
w
i
l
l
 
d
r
o
p
 
t
h
e
 
o
r
i
g
i
n
a
l
 
`
D
a
t
e
`
 
v
a
r
i
a
b
l
e
 
f
r
o
m
 
t
h
e
 
d
a
t
a
s
e
t
.



```python
#
 
d
r
o
p
 
t
h
e
 
o
r
i
g
i
n
a
l
 
D
a
t
e
 
v
a
r
i
a
b
l
e


d
f
.
d
r
o
p
(
'
D
a
t
e
'
,
 
a
x
i
s
=
1
,
 
i
n
p
l
a
c
e
 
=
 
T
r
u
e
)
```


```python
#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t
 
a
g
a
i
n


d
f
.
h
e
a
d
(
)
```

<pre>
 
 
L
o
c
a
t
i
o
n
 
 
M
i
n
T
e
m
p
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
W
i
n
d
G
u
s
t
D
i
r
 
 
\

0
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
3
.
4
 
 
 
 
 
2
2
.
9
 
 
 
 
 
 
 
0
.
6
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 

1
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
7
.
4
 
 
 
 
 
2
5
.
1
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
W
N
W
 
 
 

2
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
2
.
9
 
 
 
 
 
2
5
.
7
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
W
S
W
 
 
 

3
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
9
.
2
 
 
 
 
 
2
8
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
N
E
 
 
 

4
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
7
.
5
 
 
 
 
 
3
2
.
3
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 


 
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
W
i
n
d
D
i
r
9
a
m
 
W
i
n
d
D
i
r
3
p
m
 
 
.
.
.
 
 
P
r
e
s
s
u
r
e
3
p
m
 
 
C
l
o
u
d
9
a
m
 
 
C
l
o
u
d
3
p
m
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
W
N
W
 
 
.
.
.
 
 
 
 
 
 
 
1
0
0
7
.
1
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
N
a
N
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
N
N
W
 
 
 
 
 
 
 
 
W
S
W
 
 
.
.
.
 
 
 
 
 
 
 
1
0
0
7
.
8
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
4
6
.
0
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
W
S
W
 
 
.
.
.
 
 
 
 
 
 
 
1
0
0
8
.
7
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
2
.
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
 
 
S
E
 
 
 
 
 
 
 
 
 
 
E
 
 
.
.
.
 
 
 
 
 
 
 
1
0
1
2
.
8
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
4
1
.
0
 
 
 
 
 
 
 
 
E
N
E
 
 
 
 
 
 
 
 
 
N
W
 
 
.
.
.
 
 
 
 
 
 
 
1
0
0
6
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 


 
 
 
T
e
m
p
9
a
m
 
 
T
e
m
p
3
p
m
 
 
R
a
i
n
T
o
d
a
y
 
 
R
a
i
n
T
o
m
o
r
r
o
w
 
 
Y
e
a
r
 
 
M
o
n
t
h
 
 
D
a
y
 
 

0
 
 
 
 
 
1
6
.
9
 
 
 
 
 
2
1
.
8
 
 
 
 
 
 
 
 
 
N
o
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
1
 
 

1
 
 
 
 
 
1
7
.
2
 
 
 
 
 
2
4
.
3
 
 
 
 
 
 
 
 
 
N
o
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
2
 
 

2
 
 
 
 
 
2
1
.
0
 
 
 
 
 
2
3
.
2
 
 
 
 
 
 
 
 
 
N
o
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
3
 
 

3
 
 
 
 
 
1
8
.
1
 
 
 
 
 
2
6
.
5
 
 
 
 
 
 
 
 
 
N
o
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
4
 
 

4
 
 
 
 
 
1
7
.
8
 
 
 
 
 
2
9
.
7
 
 
 
 
 
 
 
 
 
N
o
 
 
 
 
 
 
 
 
 
 
 
 
N
o
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
5
 
 


[
5
 
r
o
w
s
 
x
 
2
5
 
c
o
l
u
m
n
s
]
</pre>
N
o
w
,
 
w
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
 
`
D
a
t
e
`
 
v
a
r
i
a
b
l
e
 
h
a
s
 
b
e
e
n
 
r
e
m
o
v
e
d
 
f
r
o
m
 
t
h
e
 
d
a
t
a
s
e
t
.




#
#
#
 
E
x
p
l
o
r
e
 
C
a
t
e
g
o
r
i
c
a
l
 
V
a
r
i
a
b
l
e
s






N
o
w
,
 
I
 
w
i
l
l
 
e
x
p
l
o
r
e
 
t
h
e
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
o
n
e
 
b
y
 
o
n
e
.
 



```python
#
 
f
i
n
d
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


c
a
t
e
g
o
r
i
c
a
l
 
=
 
[
v
a
r
 
f
o
r
 
v
a
r
 
i
n
 
d
f
.
c
o
l
u
m
n
s
 
i
f
 
d
f
[
v
a
r
]
.
d
t
y
p
e
=
=
'
O
'
]


p
r
i
n
t
(
'
T
h
e
r
e
 
a
r
e
 
{
}
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
\
n
'
.
f
o
r
m
a
t
(
l
e
n
(
c
a
t
e
g
o
r
i
c
a
l
)
)
)


p
r
i
n
t
(
'
T
h
e
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
a
r
e
 
:
'
,
 
c
a
t
e
g
o
r
i
c
a
l
)
```

<pre>
T
h
e
r
e
 
a
r
e
 
6
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


T
h
e
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
a
r
e
 
:
 
[
'
L
o
c
a
t
i
o
n
'
,
 
'
W
i
n
d
G
u
s
t
D
i
r
'
,
 
'
W
i
n
d
D
i
r
9
a
m
'
,
 
'
W
i
n
d
D
i
r
3
p
m
'
,
 
'
R
a
i
n
T
o
d
a
y
'
,
 
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]

</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
r
e
 
a
r
e
 
6
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
t
h
e
 
d
a
t
a
s
e
t
.
 
T
h
e
 
`
D
a
t
e
`
 
v
a
r
i
a
b
l
e
 
h
a
s
 
b
e
e
n
 
r
e
m
o
v
e
d
.
 
F
i
r
s
t
,
 
I
 
w
i
l
l
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
.



```python
#
 
c
h
e
c
k
 
f
o
r
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 


d
f
[
c
a
t
e
g
o
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
1
0
3
2
6

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
1
0
5
6
6

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
4
2
2
8

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
3
2
6
1

R
a
i
n
T
o
m
o
r
r
o
w
 
 
 
 
 
3
2
6
7

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
`
W
i
n
d
G
u
s
t
D
i
r
`
,
 
`
W
i
n
d
D
i
r
9
a
m
`
,
 
`
W
i
n
d
D
i
r
3
p
m
`
,
 
`
R
a
i
n
T
o
d
a
y
`
 
v
a
r
i
a
b
l
e
s
 
c
o
n
t
a
i
n
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
.
 
I
 
w
i
l
l
 
e
x
p
l
o
r
e
 
t
h
e
s
e
 
v
a
r
i
a
b
l
e
s
 
o
n
e
 
b
y
 
o
n
e
.


#
#
#
 
E
x
p
l
o
r
e
 
`
L
o
c
a
t
i
o
n
`
 
v
a
r
i
a
b
l
e



```python
#
 
p
r
i
n
t
 
n
u
m
b
e
r
 
o
f
 
l
a
b
e
l
s
 
i
n
 
L
o
c
a
t
i
o
n
 
v
a
r
i
a
b
l
e


p
r
i
n
t
(
'
L
o
c
a
t
i
o
n
 
c
o
n
t
a
i
n
s
'
,
 
l
e
n
(
d
f
.
L
o
c
a
t
i
o
n
.
u
n
i
q
u
e
(
)
)
,
 
'
l
a
b
e
l
s
'
)
```

<pre>
L
o
c
a
t
i
o
n
 
c
o
n
t
a
i
n
s
 
4
9
 
l
a
b
e
l
s

</pre>

```python
#
 
c
h
e
c
k
 
l
a
b
e
l
s
 
i
n
 
l
o
c
a
t
i
o
n
 
v
a
r
i
a
b
l
e


d
f
.
L
o
c
a
t
i
o
n
.
u
n
i
q
u
e
(
)
```

<pre>
a
r
r
a
y
(
[
'
A
l
b
u
r
y
'
,
 
'
B
a
d
g
e
r
y
s
C
r
e
e
k
'
,
 
'
C
o
b
a
r
'
,
 
'
C
o
f
f
s
H
a
r
b
o
u
r
'
,
 
'
M
o
r
e
e
'
,

 
 
 
 
 
 
 
'
N
e
w
c
a
s
t
l
e
'
,
 
'
N
o
r
a
h
H
e
a
d
'
,
 
'
N
o
r
f
o
l
k
I
s
l
a
n
d
'
,
 
'
P
e
n
r
i
t
h
'
,
 
'
R
i
c
h
m
o
n
d
'
,

 
 
 
 
 
 
 
'
S
y
d
n
e
y
'
,
 
'
S
y
d
n
e
y
A
i
r
p
o
r
t
'
,
 
'
W
a
g
g
a
W
a
g
g
a
'
,
 
'
W
i
l
l
i
a
m
t
o
w
n
'
,

 
 
 
 
 
 
 
'
W
o
l
l
o
n
g
o
n
g
'
,
 
'
C
a
n
b
e
r
r
a
'
,
 
'
T
u
g
g
e
r
a
n
o
n
g
'
,
 
'
M
o
u
n
t
G
i
n
i
n
i
'
,
 
'
B
a
l
l
a
r
a
t
'
,

 
 
 
 
 
 
 
'
B
e
n
d
i
g
o
'
,
 
'
S
a
l
e
'
,
 
'
M
e
l
b
o
u
r
n
e
A
i
r
p
o
r
t
'
,
 
'
M
e
l
b
o
u
r
n
e
'
,
 
'
M
i
l
d
u
r
a
'
,

 
 
 
 
 
 
 
'
N
h
i
l
'
,
 
'
P
o
r
t
l
a
n
d
'
,
 
'
W
a
t
s
o
n
i
a
'
,
 
'
D
a
r
t
m
o
o
r
'
,
 
'
B
r
i
s
b
a
n
e
'
,
 
'
C
a
i
r
n
s
'
,

 
 
 
 
 
 
 
'
G
o
l
d
C
o
a
s
t
'
,
 
'
T
o
w
n
s
v
i
l
l
e
'
,
 
'
A
d
e
l
a
i
d
e
'
,
 
'
M
o
u
n
t
G
a
m
b
i
e
r
'
,
 
'
N
u
r
i
o
o
t
p
a
'
,

 
 
 
 
 
 
 
'
W
o
o
m
e
r
a
'
,
 
'
A
l
b
a
n
y
'
,
 
'
W
i
t
c
h
c
l
i
f
f
e
'
,
 
'
P
e
a
r
c
e
R
A
A
F
'
,
 
'
P
e
r
t
h
A
i
r
p
o
r
t
'
,

 
 
 
 
 
 
 
'
P
e
r
t
h
'
,
 
'
S
a
l
m
o
n
G
u
m
s
'
,
 
'
W
a
l
p
o
l
e
'
,
 
'
H
o
b
a
r
t
'
,
 
'
L
a
u
n
c
e
s
t
o
n
'
,

 
 
 
 
 
 
 
'
A
l
i
c
e
S
p
r
i
n
g
s
'
,
 
'
D
a
r
w
i
n
'
,
 
'
K
a
t
h
e
r
i
n
e
'
,
 
'
U
l
u
r
u
'
]
,
 
d
t
y
p
e
=
o
b
j
e
c
t
)
</pre>

```python
#
 
c
h
e
c
k
 
f
r
e
q
u
e
n
c
y
 
d
i
s
t
r
i
b
u
t
i
o
n
 
o
f
 
v
a
l
u
e
s
 
i
n
 
L
o
c
a
t
i
o
n
 
v
a
r
i
a
b
l
e


d
f
.
L
o
c
a
t
i
o
n
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
C
a
n
b
e
r
r
a
 
 
 
 
 
 
 
 
 
 
 
 
3
4
3
6

S
y
d
n
e
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
3
4
4

H
o
b
a
r
t
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

D
a
r
w
i
n
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

B
r
i
s
b
a
n
e
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

P
e
r
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

A
d
e
l
a
i
d
e
 
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

M
e
l
b
o
u
r
n
e
 
 
 
 
 
 
 
 
 
 
 
3
1
9
3

A
l
b
a
n
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

M
o
u
n
t
G
i
n
i
n
i
 
 
 
 
 
 
 
 
 
3
0
4
0

T
o
w
n
s
v
i
l
l
e
 
 
 
 
 
 
 
 
 
 
3
0
4
0

M
o
u
n
t
G
a
m
b
i
e
r
 
 
 
 
 
 
 
 
3
0
4
0

G
o
l
d
C
o
a
s
t
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

L
a
u
n
c
e
s
t
o
n
 
 
 
 
 
 
 
 
 
 
3
0
4
0

A
l
i
c
e
S
p
r
i
n
g
s
 
 
 
 
 
 
 
 
3
0
4
0

B
a
l
l
a
r
a
t
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

W
o
l
l
o
n
g
o
n
g
 
 
 
 
 
 
 
 
 
 
3
0
4
0

C
a
i
r
n
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

B
e
n
d
i
g
o
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
4
0

N
e
w
c
a
s
t
l
e
 
 
 
 
 
 
 
 
 
 
 
3
0
3
9

T
u
g
g
e
r
a
n
o
n
g
 
 
 
 
 
 
 
 
 
3
0
3
9

P
e
n
r
i
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
3
9

N
u
r
i
o
o
t
p
a
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

P
o
r
t
l
a
n
d
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

M
o
r
e
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

M
i
l
d
u
r
a
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

N
o
r
f
o
l
k
I
s
l
a
n
d
 
 
 
 
 
 
 
3
0
0
9

R
i
c
h
m
o
n
d
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

M
e
l
b
o
u
r
n
e
A
i
r
p
o
r
t
 
 
 
 
3
0
0
9

W
o
o
m
e
r
a
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

C
o
b
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

W
a
t
s
o
n
i
a
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

W
a
g
g
a
W
a
g
g
a
 
 
 
 
 
 
 
 
 
 
3
0
0
9

P
e
r
t
h
A
i
r
p
o
r
t
 
 
 
 
 
 
 
 
3
0
0
9

B
a
d
g
e
r
y
s
C
r
e
e
k
 
 
 
 
 
 
 
3
0
0
9

S
y
d
n
e
y
A
i
r
p
o
r
t
 
 
 
 
 
 
 
3
0
0
9

P
e
a
r
c
e
R
A
A
F
 
 
 
 
 
 
 
 
 
 
3
0
0
9

C
o
f
f
s
H
a
r
b
o
u
r
 
 
 
 
 
 
 
 
3
0
0
9

W
i
t
c
h
c
l
i
f
f
e
 
 
 
 
 
 
 
 
 
3
0
0
9

S
a
l
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

D
a
r
t
m
o
o
r
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
9

W
i
l
l
i
a
m
t
o
w
n
 
 
 
 
 
 
 
 
 
3
0
0
9

W
a
l
p
o
l
e
 
 
 
 
 
 
 
 
 
 
 
 
 
3
0
0
6

N
o
r
a
h
H
e
a
d
 
 
 
 
 
 
 
 
 
 
 
3
0
0
4

S
a
l
m
o
n
G
u
m
s
 
 
 
 
 
 
 
 
 
 
3
0
0
1

N
h
i
l
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
5
7
8

U
l
u
r
u
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
5
7
8

K
a
t
h
e
r
i
n
e
 
 
 
 
 
 
 
 
 
 
 
1
5
7
8

N
a
m
e
:
 
L
o
c
a
t
i
o
n
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
l
e
t
'
s
 
d
o
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 
o
f
 
L
o
c
a
t
i
o
n
 
v
a
r
i
a
b
l
e

#
 
g
e
t
 
k
-
1
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
s
 
a
f
t
e
r
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 

#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t
 
w
i
t
h
 
h
e
a
d
(
)
 
m
e
t
h
o
d


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
L
o
c
a
t
i
o
n
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
)
.
h
e
a
d
(
)
```

<pre>
 
 
 
A
l
b
a
n
y
 
 
A
l
b
u
r
y
 
 
A
l
i
c
e
S
p
r
i
n
g
s
 
 
B
a
d
g
e
r
y
s
C
r
e
e
k
 
 
B
a
l
l
a
r
a
t
 
 
B
e
n
d
i
g
o
 
 
B
r
i
s
b
a
n
e
 
 
\

0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 


 
 
 
C
a
i
r
n
s
 
 
C
a
n
b
e
r
r
a
 
 
C
o
b
a
r
 
 
.
.
.
 
 
T
o
w
n
s
v
i
l
l
e
 
 
T
u
g
g
e
r
a
n
o
n
g
 
 
U
l
u
r
u
 
 
W
a
g
g
a
W
a
g
g
a
 
 
\

0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 


 
 
 
W
a
l
p
o
l
e
 
 
W
a
t
s
o
n
i
a
 
 
W
i
l
l
i
a
m
t
o
w
n
 
 
W
i
t
c
h
c
l
i
f
f
e
 
 
W
o
l
l
o
n
g
o
n
g
 
 
W
o
o
m
e
r
a
 
 

0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

2
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

3
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 


[
5
 
r
o
w
s
 
x
 
4
8
 
c
o
l
u
m
n
s
]
</pre>
#
#
#
 
E
x
p
l
o
r
e
 
`
W
i
n
d
G
u
s
t
D
i
r
`
 
v
a
r
i
a
b
l
e



```python
#
 
p
r
i
n
t
 
n
u
m
b
e
r
 
o
f
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e


p
r
i
n
t
(
'
W
i
n
d
G
u
s
t
D
i
r
 
c
o
n
t
a
i
n
s
'
,
 
l
e
n
(
d
f
[
'
W
i
n
d
G
u
s
t
D
i
r
'
]
.
u
n
i
q
u
e
(
)
)
,
 
'
l
a
b
e
l
s
'
)
```

<pre>
W
i
n
d
G
u
s
t
D
i
r
 
c
o
n
t
a
i
n
s
 
1
7
 
l
a
b
e
l
s

</pre>

```python
#
 
c
h
e
c
k
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e


d
f
[
'
W
i
n
d
G
u
s
t
D
i
r
'
]
.
u
n
i
q
u
e
(
)
```

<pre>
a
r
r
a
y
(
[
'
W
'
,
 
'
W
N
W
'
,
 
'
W
S
W
'
,
 
'
N
E
'
,
 
'
N
N
W
'
,
 
'
N
'
,
 
'
N
N
E
'
,
 
'
S
W
'
,
 
n
a
n
,
 
'
E
N
E
'
,

 
 
 
 
 
 
 
'
S
S
E
'
,
 
'
S
'
,
 
'
N
W
'
,
 
'
S
E
'
,
 
'
E
S
E
'
,
 
'
E
'
,
 
'
S
S
W
'
]
,
 
d
t
y
p
e
=
o
b
j
e
c
t
)
</pre>

```python
#
 
c
h
e
c
k
 
f
r
e
q
u
e
n
c
y
 
d
i
s
t
r
i
b
u
t
i
o
n
 
o
f
 
v
a
l
u
e
s
 
i
n
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e


d
f
.
W
i
n
d
G
u
s
t
D
i
r
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
W
 
 
 
 
 
 
9
9
1
5

S
E
 
 
 
 
 
9
4
1
8

N
 
 
 
 
 
 
9
3
1
3

S
S
E
 
 
 
 
9
2
1
6

E
 
 
 
 
 
 
9
1
8
1

S
 
 
 
 
 
 
9
1
6
8

W
S
W
 
 
 
 
9
0
6
9

S
W
 
 
 
 
 
8
9
6
7

S
S
W
 
 
 
 
8
7
3
6

W
N
W
 
 
 
 
8
2
5
2

N
W
 
 
 
 
 
8
1
2
2

E
N
E
 
 
 
 
8
1
0
4

E
S
E
 
 
 
 
7
3
7
2

N
E
 
 
 
 
 
7
1
3
3

N
N
W
 
 
 
 
6
6
2
0

N
N
E
 
 
 
 
6
5
4
8

N
a
m
e
:
 
W
i
n
d
G
u
s
t
D
i
r
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
l
e
t
'
s
 
d
o
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 
o
f
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e

#
 
g
e
t
 
k
-
1
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
s
 
a
f
t
e
r
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 

#
 
a
l
s
o
 
a
d
d
 
a
n
 
a
d
d
i
t
i
o
n
a
l
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
 
t
o
 
i
n
d
i
c
a
t
e
 
t
h
e
r
e
 
w
a
s
 
m
i
s
s
i
n
g
 
d
a
t
a

#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t
 
w
i
t
h
 
h
e
a
d
(
)
 
m
e
t
h
o
d


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
W
i
n
d
G
u
s
t
D
i
r
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
h
e
a
d
(
)
```

<pre>
 
 
 
E
N
E
 
 
E
S
E
 
 
N
 
 
N
E
 
 
N
N
E
 
 
N
N
W
 
 
N
W
 
 
S
 
 
S
E
 
 
S
S
E
 
 
S
S
W
 
 
S
W
 
 
W
 
 
W
N
W
 
 
W
S
W
 
 
N
a
N

0
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

1
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
1
 
 
 
 
0
 
 
 
 
0

2
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
1
 
 
 
 
0

3
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

4
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
</pre>

```python
#
 
s
u
m
 
t
h
e
 
n
u
m
b
e
r
 
o
f
 
1
s
 
p
e
r
 
b
o
o
l
e
a
n
 
v
a
r
i
a
b
l
e
 
o
v
e
r
 
t
h
e
 
r
o
w
s
 
o
f
 
t
h
e
 
d
a
t
a
s
e
t

#
 
i
t
 
w
i
l
l
 
t
e
l
l
 
u
s
 
h
o
w
 
m
a
n
y
 
o
b
s
e
r
v
a
t
i
o
n
s
 
w
e
 
h
a
v
e
 
f
o
r
 
e
a
c
h
 
c
a
t
e
g
o
r
y


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
W
i
n
d
G
u
s
t
D
i
r
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
s
u
m
(
a
x
i
s
=
0
)
```

<pre>
E
N
E
 
 
 
 
 
8
1
0
4

E
S
E
 
 
 
 
 
7
3
7
2

N
 
 
 
 
 
 
 
9
3
1
3

N
E
 
 
 
 
 
 
7
1
3
3

N
N
E
 
 
 
 
 
6
5
4
8

N
N
W
 
 
 
 
 
6
6
2
0

N
W
 
 
 
 
 
 
8
1
2
2

S
 
 
 
 
 
 
 
9
1
6
8

S
E
 
 
 
 
 
 
9
4
1
8

S
S
E
 
 
 
 
 
9
2
1
6

S
S
W
 
 
 
 
 
8
7
3
6

S
W
 
 
 
 
 
 
8
9
6
7

W
 
 
 
 
 
 
 
9
9
1
5

W
N
W
 
 
 
 
 
8
2
5
2

W
S
W
 
 
 
 
 
9
0
6
9

N
a
N
 
 
 
 
1
0
3
2
6

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
r
e
 
a
r
e
 
9
3
3
0
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e
.


#
#
#
 
E
x
p
l
o
r
e
 
`
W
i
n
d
D
i
r
9
a
m
`
 
v
a
r
i
a
b
l
e



```python
#
 
p
r
i
n
t
 
n
u
m
b
e
r
 
o
f
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
D
i
r
9
a
m
 
v
a
r
i
a
b
l
e


p
r
i
n
t
(
'
W
i
n
d
D
i
r
9
a
m
 
c
o
n
t
a
i
n
s
'
,
 
l
e
n
(
d
f
[
'
W
i
n
d
D
i
r
9
a
m
'
]
.
u
n
i
q
u
e
(
)
)
,
 
'
l
a
b
e
l
s
'
)
```

<pre>
W
i
n
d
D
i
r
9
a
m
 
c
o
n
t
a
i
n
s
 
1
7
 
l
a
b
e
l
s

</pre>

```python
#
 
c
h
e
c
k
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
D
i
r
9
a
m
 
v
a
r
i
a
b
l
e


d
f
[
'
W
i
n
d
D
i
r
9
a
m
'
]
.
u
n
i
q
u
e
(
)
```

<pre>
a
r
r
a
y
(
[
'
W
'
,
 
'
N
N
W
'
,
 
'
S
E
'
,
 
'
E
N
E
'
,
 
'
S
W
'
,
 
'
S
S
E
'
,
 
'
S
'
,
 
'
N
E
'
,
 
n
a
n
,
 
'
S
S
W
'
,
 
'
N
'
,

 
 
 
 
 
 
 
'
W
S
W
'
,
 
'
E
S
E
'
,
 
'
E
'
,
 
'
N
W
'
,
 
'
W
N
W
'
,
 
'
N
N
E
'
]
,
 
d
t
y
p
e
=
o
b
j
e
c
t
)
</pre>

```python
#
 
c
h
e
c
k
 
f
r
e
q
u
e
n
c
y
 
d
i
s
t
r
i
b
u
t
i
o
n
 
o
f
 
v
a
l
u
e
s
 
i
n
 
W
i
n
d
D
i
r
9
a
m
 
v
a
r
i
a
b
l
e


d
f
[
'
W
i
n
d
D
i
r
9
a
m
'
]
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
N
 
 
 
 
 
 
1
1
7
5
8

S
E
 
 
 
 
 
 
9
2
8
7

E
 
 
 
 
 
 
 
9
1
7
6

S
S
E
 
 
 
 
 
9
1
1
2

N
W
 
 
 
 
 
 
8
7
4
9

S
 
 
 
 
 
 
 
8
6
5
9

W
 
 
 
 
 
 
 
8
4
5
9

S
W
 
 
 
 
 
 
8
4
2
3

N
N
E
 
 
 
 
 
8
1
2
9

N
N
W
 
 
 
 
 
7
9
8
0

E
N
E
 
 
 
 
 
7
8
3
6

N
E
 
 
 
 
 
 
7
6
7
1

E
S
E
 
 
 
 
 
7
6
3
0

S
S
W
 
 
 
 
 
7
5
8
7

W
N
W
 
 
 
 
 
7
4
1
4

W
S
W
 
 
 
 
 
7
0
2
4

N
a
m
e
:
 
W
i
n
d
D
i
r
9
a
m
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
l
e
t
'
s
 
d
o
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 
o
f
 
W
i
n
d
D
i
r
9
a
m
 
v
a
r
i
a
b
l
e

#
 
g
e
t
 
k
-
1
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
s
 
a
f
t
e
r
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 

#
 
a
l
s
o
 
a
d
d
 
a
n
 
a
d
d
i
t
i
o
n
a
l
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
 
t
o
 
i
n
d
i
c
a
t
e
 
t
h
e
r
e
 
w
a
s
 
m
i
s
s
i
n
g
 
d
a
t
a

#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t
 
w
i
t
h
 
h
e
a
d
(
)
 
m
e
t
h
o
d


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
W
i
n
d
D
i
r
9
a
m
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
h
e
a
d
(
)
```

<pre>
 
 
 
E
N
E
 
 
E
S
E
 
 
N
 
 
N
E
 
 
N
N
E
 
 
N
N
W
 
 
N
W
 
 
S
 
 
S
E
 
 
S
S
E
 
 
S
S
W
 
 
S
W
 
 
W
 
 
W
N
W
 
 
W
S
W
 
 
N
a
N

0
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

1
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
1
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

2
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

3
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

4
 
 
 
 
1
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
</pre>

```python
#
 
s
u
m
 
t
h
e
 
n
u
m
b
e
r
 
o
f
 
1
s
 
p
e
r
 
b
o
o
l
e
a
n
 
v
a
r
i
a
b
l
e
 
o
v
e
r
 
t
h
e
 
r
o
w
s
 
o
f
 
t
h
e
 
d
a
t
a
s
e
t

#
 
i
t
 
w
i
l
l
 
t
e
l
l
 
u
s
 
h
o
w
 
m
a
n
y
 
o
b
s
e
r
v
a
t
i
o
n
s
 
w
e
 
h
a
v
e
 
f
o
r
 
e
a
c
h
 
c
a
t
e
g
o
r
y


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
W
i
n
d
D
i
r
9
a
m
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
s
u
m
(
a
x
i
s
=
0
)
```

<pre>
E
N
E
 
 
 
 
 
7
8
3
6

E
S
E
 
 
 
 
 
7
6
3
0

N
 
 
 
 
 
 
1
1
7
5
8

N
E
 
 
 
 
 
 
7
6
7
1

N
N
E
 
 
 
 
 
8
1
2
9

N
N
W
 
 
 
 
 
7
9
8
0

N
W
 
 
 
 
 
 
8
7
4
9

S
 
 
 
 
 
 
 
8
6
5
9

S
E
 
 
 
 
 
 
9
2
8
7

S
S
E
 
 
 
 
 
9
1
1
2

S
S
W
 
 
 
 
 
7
5
8
7

S
W
 
 
 
 
 
 
8
4
2
3

W
 
 
 
 
 
 
 
8
4
5
9

W
N
W
 
 
 
 
 
7
4
1
4

W
S
W
 
 
 
 
 
7
0
2
4

N
a
N
 
 
 
 
1
0
5
6
6

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
r
e
 
a
r
e
 
1
0
0
1
3
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
t
h
e
 
`
W
i
n
d
D
i
r
9
a
m
`
 
v
a
r
i
a
b
l
e
.


#
#
#
 
E
x
p
l
o
r
e
 
`
W
i
n
d
D
i
r
3
p
m
`
 
v
a
r
i
a
b
l
e



```python
#
 
p
r
i
n
t
 
n
u
m
b
e
r
 
o
f
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
D
i
r
3
p
m
 
v
a
r
i
a
b
l
e


p
r
i
n
t
(
'
W
i
n
d
D
i
r
3
p
m
 
c
o
n
t
a
i
n
s
'
,
 
l
e
n
(
d
f
[
'
W
i
n
d
D
i
r
3
p
m
'
]
.
u
n
i
q
u
e
(
)
)
,
 
'
l
a
b
e
l
s
'
)
```

<pre>
W
i
n
d
D
i
r
3
p
m
 
c
o
n
t
a
i
n
s
 
1
7
 
l
a
b
e
l
s

</pre>

```python
#
 
c
h
e
c
k
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
D
i
r
3
p
m
 
v
a
r
i
a
b
l
e


d
f
[
'
W
i
n
d
D
i
r
3
p
m
'
]
.
u
n
i
q
u
e
(
)
```

<pre>
a
r
r
a
y
(
[
'
W
N
W
'
,
 
'
W
S
W
'
,
 
'
E
'
,
 
'
N
W
'
,
 
'
W
'
,
 
'
S
S
E
'
,
 
'
E
S
E
'
,
 
'
E
N
E
'
,
 
'
N
N
W
'
,
 
'
S
S
W
'
,

 
 
 
 
 
 
 
'
S
W
'
,
 
'
S
E
'
,
 
'
N
'
,
 
'
S
'
,
 
'
N
N
E
'
,
 
n
a
n
,
 
'
N
E
'
]
,
 
d
t
y
p
e
=
o
b
j
e
c
t
)
</pre>

```python
#
 
c
h
e
c
k
 
f
r
e
q
u
e
n
c
y
 
d
i
s
t
r
i
b
u
t
i
o
n
 
o
f
 
v
a
l
u
e
s
 
i
n
 
W
i
n
d
D
i
r
3
p
m
 
v
a
r
i
a
b
l
e


d
f
[
'
W
i
n
d
D
i
r
3
p
m
'
]
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
S
E
 
 
 
 
 
1
0
8
3
8

W
 
 
 
 
 
 
1
0
1
1
0

S
 
 
 
 
 
 
 
9
9
2
6

W
S
W
 
 
 
 
 
9
5
1
8

S
S
E
 
 
 
 
 
9
3
9
9

S
W
 
 
 
 
 
 
9
3
5
4

N
 
 
 
 
 
 
 
8
8
9
0

W
N
W
 
 
 
 
 
8
8
7
4

N
W
 
 
 
 
 
 
8
6
1
0

E
S
E
 
 
 
 
 
8
5
0
5

E
 
 
 
 
 
 
 
8
4
7
2

N
E
 
 
 
 
 
 
8
2
6
3

S
S
W
 
 
 
 
 
8
1
5
6

N
N
W
 
 
 
 
 
7
8
7
0

E
N
E
 
 
 
 
 
7
8
5
7

N
N
E
 
 
 
 
 
6
5
9
0

N
a
m
e
:
 
W
i
n
d
D
i
r
3
p
m
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
l
e
t
'
s
 
d
o
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 
o
f
 
W
i
n
d
D
i
r
3
p
m
 
v
a
r
i
a
b
l
e

#
 
g
e
t
 
k
-
1
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
s
 
a
f
t
e
r
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 

#
 
a
l
s
o
 
a
d
d
 
a
n
 
a
d
d
i
t
i
o
n
a
l
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
 
t
o
 
i
n
d
i
c
a
t
e
 
t
h
e
r
e
 
w
a
s
 
m
i
s
s
i
n
g
 
d
a
t
a

#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t
 
w
i
t
h
 
h
e
a
d
(
)
 
m
e
t
h
o
d


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
W
i
n
d
D
i
r
3
p
m
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
h
e
a
d
(
)
```

<pre>
 
 
 
E
N
E
 
 
E
S
E
 
 
N
 
 
N
E
 
 
N
N
E
 
 
N
N
W
 
 
N
W
 
 
S
 
 
S
E
 
 
S
S
E
 
 
S
S
W
 
 
S
W
 
 
W
 
 
W
N
W
 
 
W
S
W
 
 
N
a
N

0
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
1
 
 
 
 
0
 
 
 
 
0

1
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
1
 
 
 
 
0

2
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
1
 
 
 
 
0

3
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0

4
 
 
 
 
0
 
 
 
 
0
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
1
 
 
0
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
</pre>

```python
#
 
s
u
m
 
t
h
e
 
n
u
m
b
e
r
 
o
f
 
1
s
 
p
e
r
 
b
o
o
l
e
a
n
 
v
a
r
i
a
b
l
e
 
o
v
e
r
 
t
h
e
 
r
o
w
s
 
o
f
 
t
h
e
 
d
a
t
a
s
e
t

#
 
i
t
 
w
i
l
l
 
t
e
l
l
 
u
s
 
h
o
w
 
m
a
n
y
 
o
b
s
e
r
v
a
t
i
o
n
s
 
w
e
 
h
a
v
e
 
f
o
r
 
e
a
c
h
 
c
a
t
e
g
o
r
y


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
W
i
n
d
D
i
r
3
p
m
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
s
u
m
(
a
x
i
s
=
0
)
```

<pre>
E
N
E
 
 
 
 
 
7
8
5
7

E
S
E
 
 
 
 
 
8
5
0
5

N
 
 
 
 
 
 
 
8
8
9
0

N
E
 
 
 
 
 
 
8
2
6
3

N
N
E
 
 
 
 
 
6
5
9
0

N
N
W
 
 
 
 
 
7
8
7
0

N
W
 
 
 
 
 
 
8
6
1
0

S
 
 
 
 
 
 
 
9
9
2
6

S
E
 
 
 
 
 
1
0
8
3
8

S
S
E
 
 
 
 
 
9
3
9
9

S
S
W
 
 
 
 
 
8
1
5
6

S
W
 
 
 
 
 
 
9
3
5
4

W
 
 
 
 
 
 
1
0
1
1
0

W
N
W
 
 
 
 
 
8
8
7
4

W
S
W
 
 
 
 
 
9
5
1
8

N
a
N
 
 
 
 
 
4
2
2
8

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
T
h
e
r
e
 
a
r
e
 
3
7
7
8
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
t
h
e
 
`
W
i
n
d
D
i
r
3
p
m
`
 
v
a
r
i
a
b
l
e
.


#
#
#
 
E
x
p
l
o
r
e
 
`
R
a
i
n
T
o
d
a
y
`
 
v
a
r
i
a
b
l
e



```python
#
 
p
r
i
n
t
 
n
u
m
b
e
r
 
o
f
 
l
a
b
e
l
s
 
i
n
 
R
a
i
n
T
o
d
a
y
 
v
a
r
i
a
b
l
e


p
r
i
n
t
(
'
R
a
i
n
T
o
d
a
y
 
c
o
n
t
a
i
n
s
'
,
 
l
e
n
(
d
f
[
'
R
a
i
n
T
o
d
a
y
'
]
.
u
n
i
q
u
e
(
)
)
,
 
'
l
a
b
e
l
s
'
)
```

<pre>
R
a
i
n
T
o
d
a
y
 
c
o
n
t
a
i
n
s
 
3
 
l
a
b
e
l
s

</pre>

```python
#
 
c
h
e
c
k
 
l
a
b
e
l
s
 
i
n
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e


d
f
[
'
R
a
i
n
T
o
d
a
y
'
]
.
u
n
i
q
u
e
(
)
```

<pre>
a
r
r
a
y
(
[
'
N
o
'
,
 
'
Y
e
s
'
,
 
n
a
n
]
,
 
d
t
y
p
e
=
o
b
j
e
c
t
)
</pre>

```python
#
 
c
h
e
c
k
 
f
r
e
q
u
e
n
c
y
 
d
i
s
t
r
i
b
u
t
i
o
n
 
o
f
 
v
a
l
u
e
s
 
i
n
 
W
i
n
d
G
u
s
t
D
i
r
 
v
a
r
i
a
b
l
e


d
f
.
R
a
i
n
T
o
d
a
y
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
N
o
 
 
 
 
 
1
1
0
3
1
9

Y
e
s
 
 
 
 
 
3
1
8
8
0

N
a
m
e
:
 
R
a
i
n
T
o
d
a
y
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
l
e
t
'
s
 
d
o
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 
o
f
 
R
a
i
n
T
o
d
a
y
 
v
a
r
i
a
b
l
e

#
 
g
e
t
 
k
-
1
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
s
 
a
f
t
e
r
 
O
n
e
 
H
o
t
 
E
n
c
o
d
i
n
g
 

#
 
a
l
s
o
 
a
d
d
 
a
n
 
a
d
d
i
t
i
o
n
a
l
 
d
u
m
m
y
 
v
a
r
i
a
b
l
e
 
t
o
 
i
n
d
i
c
a
t
e
 
t
h
e
r
e
 
w
a
s
 
m
i
s
s
i
n
g
 
d
a
t
a

#
 
p
r
e
v
i
e
w
 
t
h
e
 
d
a
t
a
s
e
t
 
w
i
t
h
 
h
e
a
d
(
)
 
m
e
t
h
o
d


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
R
a
i
n
T
o
d
a
y
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
h
e
a
d
(
)
```

<pre>
 
 
 
Y
e
s
 
 
N
a
N

0
 
 
 
 
0
 
 
 
 
0

1
 
 
 
 
0
 
 
 
 
0

2
 
 
 
 
0
 
 
 
 
0

3
 
 
 
 
0
 
 
 
 
0

4
 
 
 
 
0
 
 
 
 
0
</pre>

```python
#
 
s
u
m
 
t
h
e
 
n
u
m
b
e
r
 
o
f
 
1
s
 
p
e
r
 
b
o
o
l
e
a
n
 
v
a
r
i
a
b
l
e
 
o
v
e
r
 
t
h
e
 
r
o
w
s
 
o
f
 
t
h
e
 
d
a
t
a
s
e
t

#
 
i
t
 
w
i
l
l
 
t
e
l
l
 
u
s
 
h
o
w
 
m
a
n
y
 
o
b
s
e
r
v
a
t
i
o
n
s
 
w
e
 
h
a
v
e
 
f
o
r
 
e
a
c
h
 
c
a
t
e
g
o
r
y


p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
d
f
.
R
a
i
n
T
o
d
a
y
,
 
d
r
o
p
_
f
i
r
s
t
=
T
r
u
e
,
 
d
u
m
m
y
_
n
a
=
T
r
u
e
)
.
s
u
m
(
a
x
i
s
=
0
)
```

<pre>
Y
e
s
 
 
 
 
3
1
8
8
0

N
a
N
 
 
 
 
 
3
2
6
1

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
T
h
e
r
e
 
a
r
e
 
1
4
0
6
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
t
h
e
 
`
R
a
i
n
T
o
d
a
y
`
 
v
a
r
i
a
b
l
e
.


#
#
#
 
E
x
p
l
o
r
e
 
N
u
m
e
r
i
c
a
l
 
V
a
r
i
a
b
l
e
s



```python
#
 
f
i
n
d
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


n
u
m
e
r
i
c
a
l
 
=
 
[
v
a
r
 
f
o
r
 
v
a
r
 
i
n
 
d
f
.
c
o
l
u
m
n
s
 
i
f
 
d
f
[
v
a
r
]
.
d
t
y
p
e
!
=
'
O
'
]


p
r
i
n
t
(
'
T
h
e
r
e
 
a
r
e
 
{
}
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
\
n
'
.
f
o
r
m
a
t
(
l
e
n
(
n
u
m
e
r
i
c
a
l
)
)
)


p
r
i
n
t
(
'
T
h
e
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
a
r
e
 
:
'
,
 
n
u
m
e
r
i
c
a
l
)
```

<pre>
T
h
e
r
e
 
a
r
e
 
1
9
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


T
h
e
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
a
r
e
 
:
 
[
'
M
i
n
T
e
m
p
'
,
 
'
M
a
x
T
e
m
p
'
,
 
'
R
a
i
n
f
a
l
l
'
,
 
'
E
v
a
p
o
r
a
t
i
o
n
'
,
 
'
S
u
n
s
h
i
n
e
'
,
 
'
W
i
n
d
G
u
s
t
S
p
e
e
d
'
,
 
'
W
i
n
d
S
p
e
e
d
9
a
m
'
,
 
'
W
i
n
d
S
p
e
e
d
3
p
m
'
,
 
'
H
u
m
i
d
i
t
y
9
a
m
'
,
 
'
H
u
m
i
d
i
t
y
3
p
m
'
,
 
'
P
r
e
s
s
u
r
e
9
a
m
'
,
 
'
P
r
e
s
s
u
r
e
3
p
m
'
,
 
'
C
l
o
u
d
9
a
m
'
,
 
'
C
l
o
u
d
3
p
m
'
,
 
'
T
e
m
p
9
a
m
'
,
 
'
T
e
m
p
3
p
m
'
,
 
'
Y
e
a
r
'
,
 
'
M
o
n
t
h
'
,
 
'
D
a
y
'
]

</pre>

```python
#
 
v
i
e
w
 
t
h
e
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


d
f
[
n
u
m
e
r
i
c
a
l
]
.
h
e
a
d
(
)
```

<pre>
 
 
 
M
i
n
T
e
m
p
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
\

0
 
 
 
 
 
1
3
.
4
 
 
 
 
 
2
2
.
9
 
 
 
 
 
 
 
0
.
6
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 

1
 
 
 
 
 
 
7
.
4
 
 
 
 
 
2
5
.
1
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 

2
 
 
 
 
 
1
2
.
9
 
 
 
 
 
2
5
.
7
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
4
6
.
0
 
 
 

3
 
 
 
 
 
 
9
.
2
 
 
 
 
 
2
8
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
2
4
.
0
 
 
 

4
 
 
 
 
 
1
7
.
5
 
 
 
 
 
3
2
.
3
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
4
1
.
0
 
 
 


 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
P
r
e
s
s
u
r
e
9
a
m
 
 
\

0
 
 
 
 
 
 
 
 
 
 
2
0
.
0
 
 
 
 
 
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
 
 
7
1
.
0
 
 
 
 
 
 
 
 
 
2
2
.
0
 
 
 
 
 
 
 
1
0
0
7
.
7
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
4
.
0
 
 
 
 
 
 
 
 
 
 
2
2
.
0
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
 
2
5
.
0
 
 
 
 
 
 
 
1
0
1
0
.
6
 
 
 

2
 
 
 
 
 
 
 
 
 
 
1
9
.
0
 
 
 
 
 
 
 
 
 
 
2
6
.
0
 
 
 
 
 
 
 
 
 
3
8
.
0
 
 
 
 
 
 
 
 
 
3
0
.
0
 
 
 
 
 
 
 
1
0
0
7
.
6
 
 
 

3
 
 
 
 
 
 
 
 
 
 
1
1
.
0
 
 
 
 
 
 
 
 
 
 
 
9
.
0
 
 
 
 
 
 
 
 
 
4
5
.
0
 
 
 
 
 
 
 
 
 
1
6
.
0
 
 
 
 
 
 
 
1
0
1
7
.
6
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
 
 
 
2
0
.
0
 
 
 
 
 
 
 
 
 
8
2
.
0
 
 
 
 
 
 
 
 
 
3
3
.
0
 
 
 
 
 
 
 
1
0
1
0
.
8
 
 
 


 
 
 
P
r
e
s
s
u
r
e
3
p
m
 
 
C
l
o
u
d
9
a
m
 
 
C
l
o
u
d
3
p
m
 
 
T
e
m
p
9
a
m
 
 
T
e
m
p
3
p
m
 
 
Y
e
a
r
 
 
M
o
n
t
h
 
 
D
a
y
 
 

0
 
 
 
 
 
 
 
1
0
0
7
.
1
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
1
6
.
9
 
 
 
 
 
2
1
.
8
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
1
 
 

1
 
 
 
 
 
 
 
1
0
0
7
.
8
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
1
7
.
2
 
 
 
 
 
2
4
.
3
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
2
 
 

2
 
 
 
 
 
 
 
1
0
0
8
.
7
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
2
1
.
0
 
 
 
 
 
2
3
.
2
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
3
 
 

3
 
 
 
 
 
 
 
1
0
1
2
.
8
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
1
8
.
1
 
 
 
 
 
2
6
.
5
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
4
 
 

4
 
 
 
 
 
 
 
1
0
0
6
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
1
7
.
8
 
 
 
 
 
2
9
.
7
 
 
2
0
0
8
 
 
 
 
 
1
2
 
 
 
 
5
 
 
</pre>
#
#
#
 
S
u
m
m
a
r
y
 
o
f
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s






-
 
T
h
e
r
e
 
a
r
e
 
1
6
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
.
 






-
 
T
h
e
s
e
 
a
r
e
 
g
i
v
e
n
 
b
y
 
`
M
i
n
T
e
m
p
`
,
 
`
M
a
x
T
e
m
p
`
,
 
`
R
a
i
n
f
a
l
l
`
,
 
`
E
v
a
p
o
r
a
t
i
o
n
`
,
 
`
S
u
n
s
h
i
n
e
`
,
 
`
W
i
n
d
G
u
s
t
S
p
e
e
d
`
,
 
`
W
i
n
d
S
p
e
e
d
9
a
m
`
,
 
`
W
i
n
d
S
p
e
e
d
3
p
m
`
,
 
`
H
u
m
i
d
i
t
y
9
a
m
`
,
 
`
H
u
m
i
d
i
t
y
3
p
m
`
,
 
`
P
r
e
s
s
u
r
e
9
a
m
`
,
 
`
P
r
e
s
s
u
r
e
3
p
m
`
,
 
`
C
l
o
u
d
9
a
m
`
,
 
`
C
l
o
u
d
3
p
m
`
,
 
`
T
e
m
p
9
a
m
`
 
a
n
d
 
`
T
e
m
p
3
p
m
`
.






-
 
A
l
l
 
o
f
 
t
h
e
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
a
r
e
 
o
f
 
c
o
n
t
i
n
u
o
u
s
 
t
y
p
e
.


#
#
 
수
치
형
 
변
수
 
내
 
결
측
치
 
탐
색


이
번
에
는
 
수
치
형
 
변
수
들
을
 
탐
색
해
보
겠
습
니
다
.




수
치
형
 
변
수
 
내
 
결
측
치


#
#
#
 
먼
저
,
 
수
치
형
 
변
수
 
내
 
결
측
치
를
 
확
인
해
보
겠
습
니
다
.



```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


d
f
[
n
u
m
e
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
 
1
4
8
5

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
 
1
2
6
1

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
 
3
2
6
1

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
6
2
7
9
0

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
6
9
8
3
5

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
1
0
2
6
3

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
 
1
7
6
7

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
 
3
0
6
2

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
 
2
6
5
4

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
 
4
5
0
7

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
1
5
0
6
5

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
1
5
0
2
8

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
5
5
8
8
8

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
5
9
3
5
8

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
 
1
7
6
7

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
 
3
6
0
9

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
a
l
l
 
t
h
e
 
1
6
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
c
o
n
t
a
i
n
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
.


#
#
#
 
O
u
t
l
i
e
r
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s



```python
#
 
v
i
e
w
 
s
u
m
m
a
r
y
 
s
t
a
t
i
s
t
i
c
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


p
r
i
n
t
(
r
o
u
n
d
(
d
f
[
n
u
m
e
r
i
c
a
l
]
.
d
e
s
c
r
i
b
e
(
)
)
,
2
)
```

<pre>
 
 
 
 
 
 
 
 
M
i
n
T
e
m
p
 
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
\

c
o
u
n
t
 
 
1
4
3
9
7
5
.
0
 
 
1
4
4
1
9
9
.
0
 
 
1
4
2
1
9
9
.
0
 
 
 
 
 
 
8
2
6
7
0
.
0
 
 
 
7
5
6
2
5
.
0
 
 
 
 
 
 
 
1
3
5
1
9
7
.
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
1
2
.
0
 
 
 
 
 
 
2
3
.
0
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
 
 
 
 
4
0
.
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
6
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
 
 
 
4
.
0
 
 
 
 
 
 
 
4
.
0
 
 
 
 
 
 
 
 
 
 
 
1
4
.
0
 
 
 

m
i
n
 
 
 
 
 
 
 
 
-
8
.
0
 
 
 
 
 
 
-
5
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
 
6
.
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
1
8
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
3
.
0
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
 
 
 
 
3
1
.
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
1
2
.
0
 
 
 
 
 
 
2
3
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
 
 
 
 
3
9
.
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
1
7
.
0
 
 
 
 
 
 
2
8
.
0
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
1
1
.
0
 
 
 
 
 
 
 
 
 
 
 
4
8
.
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
3
4
.
0
 
 
 
 
 
 
4
8
.
0
 
 
 
 
 
3
7
1
.
0
 
 
 
 
 
 
 
 
1
4
5
.
0
 
 
 
 
 
 
1
4
.
0
 
 
 
 
 
 
 
 
 
 
1
3
5
.
0
 
 
 


 
 
 
 
 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
P
r
e
s
s
u
r
e
9
a
m
 
 
\

c
o
u
n
t
 
 
 
 
 
 
1
4
3
6
9
3
.
0
 
 
 
 
 
 
1
4
2
3
9
8
.
0
 
 
 
 
 
1
4
2
8
0
6
.
0
 
 
 
 
 
1
4
0
9
5
3
.
0
 
 
 
 
 
1
3
0
3
9
5
.
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
 
 
 
1
4
.
0
 
 
 
 
 
 
 
 
 
 
1
9
.
0
 
 
 
 
 
 
 
 
 
6
9
.
0
 
 
 
 
 
 
 
 
 
5
2
.
0
 
 
 
 
 
 
 
1
0
1
8
.
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
 
 
 
 
9
.
0
 
 
 
 
 
 
 
 
 
 
 
9
.
0
 
 
 
 
 
 
 
 
 
1
9
.
0
 
 
 
 
 
 
 
 
 
2
1
.
0
 
 
 
 
 
 
 
 
 
 
7
.
0
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
9
8
0
.
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
 
 
 
1
3
.
0
 
 
 
 
 
 
 
 
 
5
7
.
0
 
 
 
 
 
 
 
 
 
3
7
.
0
 
 
 
 
 
 
 
1
0
1
3
.
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
 
 
 
1
3
.
0
 
 
 
 
 
 
 
 
 
 
1
9
.
0
 
 
 
 
 
 
 
 
 
7
0
.
0
 
 
 
 
 
 
 
 
 
5
2
.
0
 
 
 
 
 
 
 
1
0
1
8
.
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
 
 
 
1
9
.
0
 
 
 
 
 
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
 
 
8
3
.
0
 
 
 
 
 
 
 
 
 
6
6
.
0
 
 
 
 
 
 
 
1
0
2
2
.
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
 
 
1
3
0
.
0
 
 
 
 
 
 
 
 
 
 
8
7
.
0
 
 
 
 
 
 
 
 
1
0
0
.
0
 
 
 
 
 
 
 
 
1
0
0
.
0
 
 
 
 
 
 
 
1
0
4
1
.
0
 
 
 


 
 
 
 
 
 
 
P
r
e
s
s
u
r
e
3
p
m
 
 
C
l
o
u
d
9
a
m
 
 
C
l
o
u
d
3
p
m
 
 
 
T
e
m
p
9
a
m
 
 
 
T
e
m
p
3
p
m
 
 
 
 
 
 
Y
e
a
r
 
 
\

c
o
u
n
t
 
 
 
 
 
1
3
0
4
3
2
.
0
 
 
 
8
9
5
7
2
.
0
 
 
 
8
6
1
0
2
.
0
 
 
1
4
3
6
9
3
.
0
 
 
1
4
1
8
5
1
.
0
 
 
1
4
5
4
6
0
.
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
1
0
1
5
.
0
 
 
 
 
 
 
 
4
.
0
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
1
7
.
0
 
 
 
 
 
 
2
2
.
0
 
 
 
 
2
0
1
3
.
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
3
.
0
 
 
 
 
 
 
 
3
.
0
 
 
 
 
 
 
 
6
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
3
.
0
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
 
9
7
7
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
-
7
.
0
 
 
 
 
 
 
-
5
.
0
 
 
 
 
2
0
0
7
.
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
1
0
1
0
.
0
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
1
2
.
0
 
 
 
 
 
 
1
7
.
0
 
 
 
 
2
0
1
1
.
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
1
0
1
5
.
0
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
1
7
.
0
 
 
 
 
 
 
2
1
.
0
 
 
 
 
2
0
1
3
.
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
1
0
2
0
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
2
2
.
0
 
 
 
 
 
 
2
6
.
0
 
 
 
 
2
0
1
5
.
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
0
4
0
.
0
 
 
 
 
 
 
 
9
.
0
 
 
 
 
 
 
 
9
.
0
 
 
 
 
 
 
4
0
.
0
 
 
 
 
 
 
4
7
.
0
 
 
 
 
2
0
1
7
.
0
 
 
 


 
 
 
 
 
 
 
 
 
 
M
o
n
t
h
 
 
 
 
 
 
 
D
a
y
 
 

c
o
u
n
t
 
 
1
4
5
4
6
0
.
0
 
 
1
4
5
4
6
0
.
0
 
 

m
e
a
n
 
 
 
 
 
 
 
 
6
.
0
 
 
 
 
 
 
1
6
.
0
 
 

s
t
d
 
 
 
 
 
 
 
 
 
3
.
0
 
 
 
 
 
 
 
9
.
0
 
 

m
i
n
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
1
.
0
 
 

2
5
%
 
 
 
 
 
 
 
 
 
3
.
0
 
 
 
 
 
 
 
8
.
0
 
 

5
0
%
 
 
 
 
 
 
 
 
 
6
.
0
 
 
 
 
 
 
1
6
.
0
 
 

7
5
%
 
 
 
 
 
 
 
 
 
9
.
0
 
 
 
 
 
 
2
3
.
0
 
 

m
a
x
 
 
 
 
 
 
 
 
1
2
.
0
 
 
 
 
 
 
3
1
.
0
 
 
 
2

</pre>
자
세
히
 
살
펴
보
면
,
 
`
R
a
i
n
f
a
l
l
,
 
E
v
a
p
o
r
a
t
i
o
n
,
 
W
i
n
d
S
p
e
e
d
9
a
m
,
 
W
i
n
d
S
p
e
e
d
3
p
m
`
 
열
에
 
이
상
치
가
 
포
함
될
 
수
 
있
다
는
 
것
을
 
알
 
수
 
있
습
니
다
.




위
 
변
수
들
에
서
 
이
상
치
를
 
시
각
화
하
기
 
위
해
 
상
자
 
그
림
을
 
그
릴
 
것
입
니
다
.











```python
#
 
d
r
a
w
 
b
o
x
p
l
o
t
s
 
t
o
 
v
i
s
u
a
l
i
z
e
 
o
u
t
l
i
e
r
s


p
l
t
.
f
i
g
u
r
e
(
f
i
g
s
i
z
e
=
(
1
5
,
1
0
)
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
1
)

f
i
g
 
=
 
d
f
.
b
o
x
p
l
o
t
(
c
o
l
u
m
n
=
'
R
a
i
n
f
a
l
l
'
)

f
i
g
.
s
e
t
_
t
i
t
l
e
(
'
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
R
a
i
n
f
a
l
l
'
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
2
)

f
i
g
 
=
 
d
f
.
b
o
x
p
l
o
t
(
c
o
l
u
m
n
=
'
E
v
a
p
o
r
a
t
i
o
n
'
)

f
i
g
.
s
e
t
_
t
i
t
l
e
(
'
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
E
v
a
p
o
r
a
t
i
o
n
'
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
3
)

f
i
g
 
=
 
d
f
.
b
o
x
p
l
o
t
(
c
o
l
u
m
n
=
'
W
i
n
d
S
p
e
e
d
9
a
m
'
)

f
i
g
.
s
e
t
_
t
i
t
l
e
(
'
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
W
i
n
d
S
p
e
e
d
9
a
m
'
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
4
)

f
i
g
 
=
 
d
f
.
b
o
x
p
l
o
t
(
c
o
l
u
m
n
=
'
W
i
n
d
S
p
e
e
d
3
p
m
'
)

f
i
g
.
s
e
t
_
t
i
t
l
e
(
'
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
W
i
n
d
S
p
e
e
d
3
p
m
'
)
```

<pre>
T
e
x
t
(
0
,
 
0
.
5
,
 
'
W
i
n
d
S
p
e
e
d
3
p
m
'
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
1
0
8
0
x
7
2
0
 
w
i
t
h
 
4
 
A
x
e
s
>
</pre>
위
의
 
상
자
그
림
은
 
이
 
변
수
들
에
 
이
상
치
가
 
많
이
 
있
다
는
 
것
을
 
확
인
시
켜
 
줍
니
다
.


#
#
#
 
변
수
의
 
분
포
 
확
인
하
기


이
제
 
히
스
토
그
램
을
 
그
려
서
 
분
포
를
 
확
인
하
고
,
 
정
규
분
포
인
지
 
왜
도
(
s
k
e
w
n
e
s
s
)
가
 
있
는
지
 
알
아
보
겠
습
니
다
.
 
만
약
 
변
수
가
 
정
규
분
포
를
 
따
른
다
면
 
극
값
 
분
석
(
E
x
t
r
e
m
e
 
V
a
l
u
e
 
A
n
a
l
y
s
i
s
)
을
 
수
행
하
겠
지
만
,
 
왜
도
가
 
있
다
면
 
I
Q
R
(
I
n
t
e
r
q
u
a
n
t
i
l
e
 
r
a
n
g
e
)
를
 
구
할
 
것
입
니
다
.



```python
#
 
p
l
o
t
 
h
i
s
t
o
g
r
a
m
 
t
o
 
c
h
e
c
k
 
d
i
s
t
r
i
b
u
t
i
o
n


p
l
t
.
f
i
g
u
r
e
(
f
i
g
s
i
z
e
=
(
1
5
,
1
0
)
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
1
)

f
i
g
 
=
 
d
f
.
R
a
i
n
f
a
l
l
.
h
i
s
t
(
b
i
n
s
=
1
0
)

f
i
g
.
s
e
t
_
x
l
a
b
e
l
(
'
R
a
i
n
f
a
l
l
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
R
a
i
n
T
o
m
o
r
r
o
w
'
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
2
)

f
i
g
 
=
 
d
f
.
E
v
a
p
o
r
a
t
i
o
n
.
h
i
s
t
(
b
i
n
s
=
1
0
)

f
i
g
.
s
e
t
_
x
l
a
b
e
l
(
'
E
v
a
p
o
r
a
t
i
o
n
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
R
a
i
n
T
o
m
o
r
r
o
w
'
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
3
)

f
i
g
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
9
a
m
.
h
i
s
t
(
b
i
n
s
=
1
0
)

f
i
g
.
s
e
t
_
x
l
a
b
e
l
(
'
W
i
n
d
S
p
e
e
d
9
a
m
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
R
a
i
n
T
o
m
o
r
r
o
w
'
)



p
l
t
.
s
u
b
p
l
o
t
(
2
,
 
2
,
 
4
)

f
i
g
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
3
p
m
.
h
i
s
t
(
b
i
n
s
=
1
0
)

f
i
g
.
s
e
t
_
x
l
a
b
e
l
(
'
W
i
n
d
S
p
e
e
d
3
p
m
'
)

f
i
g
.
s
e
t
_
y
l
a
b
e
l
(
'
R
a
i
n
T
o
m
o
r
r
o
w
'
)
```

<pre>
T
e
x
t
(
0
,
 
0
.
5
,
 
'
R
a
i
n
T
o
m
o
r
r
o
w
'
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
1
0
8
0
x
7
2
0
 
w
i
t
h
 
4
 
A
x
e
s
>
</pre>
네
 
개
의
 
변
수
 
모
두
 
왜
도
가
 
있
는
 
것
으
로
 
보
입
니
다
.
 
그
러
므
로
,
 
외
부
값
(
o
u
t
l
i
e
r
)
을
 
찾
기
 
위
해
 
I
Q
R
(
I
n
t
e
r
q
u
a
n
t
i
l
e
 
r
a
n
g
e
)
를
 
사
용
하
겠
습
니
다
.



```python
#
 
f
i
n
d
 
o
u
t
l
i
e
r
s
 
f
o
r
 
R
a
i
n
f
a
l
l
 
v
a
r
i
a
b
l
e


I
Q
R
 
=
 
d
f
.
R
a
i
n
f
a
l
l
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
-
 
d
f
.
R
a
i
n
f
a
l
l
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)

L
o
w
e
r
_
f
e
n
c
e
 
=
 
d
f
.
R
a
i
n
f
a
l
l
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)
 
-
 
(
I
Q
R
 
*
 
3
)

U
p
p
e
r
_
f
e
n
c
e
 
=
 
d
f
.
R
a
i
n
f
a
l
l
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
+
 
(
I
Q
R
 
*
 
3
)

p
r
i
n
t
(
'
R
a
i
n
f
a
l
l
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
{
l
o
w
e
r
b
o
u
n
d
a
r
y
}
 
o
r
 
>
 
{
u
p
p
e
r
b
o
u
n
d
a
r
y
}
'
.
f
o
r
m
a
t
(
l
o
w
e
r
b
o
u
n
d
a
r
y
=
L
o
w
e
r
_
f
e
n
c
e
,
 
u
p
p
e
r
b
o
u
n
d
a
r
y
=
U
p
p
e
r
_
f
e
n
c
e
)
)

```

<pre>
R
a
i
n
f
a
l
l
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
-
2
.
4
0
0
0
0
0
0
0
0
0
0
0
0
0
0
4
 
o
r
 
>
 
3
.
2

</pre>
강
수
량
(
R
a
i
n
f
a
l
l
)
 
변
수
의
 
최
솟
값
과
 
최
댓
값
은
 
각
각
 
0
.
0
과
 
3
7
1
.
0
입
니
다
.
 
따
라
서
,
 
이
상
치
는
 
3
.
2
보
다
 
큰
 
값
입
니
다
.



```python
#
 
f
i
n
d
 
o
u
t
l
i
e
r
s
 
f
o
r
 
E
v
a
p
o
r
a
t
i
o
n
 
v
a
r
i
a
b
l
e


I
Q
R
 
=
 
d
f
.
E
v
a
p
o
r
a
t
i
o
n
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
-
 
d
f
.
E
v
a
p
o
r
a
t
i
o
n
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)

L
o
w
e
r
_
f
e
n
c
e
 
=
 
d
f
.
E
v
a
p
o
r
a
t
i
o
n
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)
 
-
 
(
I
Q
R
 
*
 
3
)

U
p
p
e
r
_
f
e
n
c
e
 
=
 
d
f
.
E
v
a
p
o
r
a
t
i
o
n
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
+
 
(
I
Q
R
 
*
 
3
)

p
r
i
n
t
(
'
E
v
a
p
o
r
a
t
i
o
n
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
{
l
o
w
e
r
b
o
u
n
d
a
r
y
}
 
o
r
 
>
 
{
u
p
p
e
r
b
o
u
n
d
a
r
y
}
'
.
f
o
r
m
a
t
(
l
o
w
e
r
b
o
u
n
d
a
r
y
=
L
o
w
e
r
_
f
e
n
c
e
,
 
u
p
p
e
r
b
o
u
n
d
a
r
y
=
U
p
p
e
r
_
f
e
n
c
e
)
)

```

<pre>
E
v
a
p
o
r
a
t
i
o
n
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
-
1
1
.
8
0
0
0
0
0
0
0
0
0
0
0
0
0
2
 
o
r
 
>
 
2
1
.
8
0
0
0
0
0
0
0
0
0
0
0
0
0
4

</pre>
증
발
량
(
E
v
a
p
o
r
a
t
i
o
n
)
 
변
수
의
 
최
솟
값
과
 
최
댓
값
은
 
각
각
 
0
.
0
과
 
1
4
5
.
0
입
니
다
.
 
따
라
서
,
 
이
상
치
는
 
2
1
.
8
보
다
 
큰
 
값
입
니
다
.



```python
#
 
f
i
n
d
 
o
u
t
l
i
e
r
s
 
f
o
r
 
W
i
n
d
S
p
e
e
d
9
a
m
 
v
a
r
i
a
b
l
e


I
Q
R
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
9
a
m
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
-
 
d
f
.
W
i
n
d
S
p
e
e
d
9
a
m
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)

L
o
w
e
r
_
f
e
n
c
e
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
9
a
m
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)
 
-
 
(
I
Q
R
 
*
 
3
)

U
p
p
e
r
_
f
e
n
c
e
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
9
a
m
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
+
 
(
I
Q
R
 
*
 
3
)

p
r
i
n
t
(
'
W
i
n
d
S
p
e
e
d
9
a
m
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
{
l
o
w
e
r
b
o
u
n
d
a
r
y
}
 
o
r
 
>
 
{
u
p
p
e
r
b
o
u
n
d
a
r
y
}
'
.
f
o
r
m
a
t
(
l
o
w
e
r
b
o
u
n
d
a
r
y
=
L
o
w
e
r
_
f
e
n
c
e
,
 
u
p
p
e
r
b
o
u
n
d
a
r
y
=
U
p
p
e
r
_
f
e
n
c
e
)
)

```

<pre>
W
i
n
d
S
p
e
e
d
9
a
m
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
-
2
9
.
0
 
o
r
 
>
 
5
5
.
0

</pre>
풍
속
9
a
m
(
W
i
n
d
S
p
e
e
d
9
a
m
)
 
변
수
의
 
최
솟
값
과
 
최
댓
값
은
 
각
각
 
0
.
0
과
 
1
3
0
.
0
입
니
다
.
 
따
라
서
,
 
이
상
치
는
 
5
5
.
0
보
다
 
큰
 
값
입
니
다
.



```python
#
 
f
i
n
d
 
o
u
t
l
i
e
r
s
 
f
o
r
 
W
i
n
d
S
p
e
e
d
3
p
m
 
v
a
r
i
a
b
l
e


I
Q
R
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
3
p
m
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
-
 
d
f
.
W
i
n
d
S
p
e
e
d
3
p
m
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)

L
o
w
e
r
_
f
e
n
c
e
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
3
p
m
.
q
u
a
n
t
i
l
e
(
0
.
2
5
)
 
-
 
(
I
Q
R
 
*
 
3
)

U
p
p
e
r
_
f
e
n
c
e
 
=
 
d
f
.
W
i
n
d
S
p
e
e
d
3
p
m
.
q
u
a
n
t
i
l
e
(
0
.
7
5
)
 
+
 
(
I
Q
R
 
*
 
3
)

p
r
i
n
t
(
'
W
i
n
d
S
p
e
e
d
3
p
m
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
{
l
o
w
e
r
b
o
u
n
d
a
r
y
}
 
o
r
 
>
 
{
u
p
p
e
r
b
o
u
n
d
a
r
y
}
'
.
f
o
r
m
a
t
(
l
o
w
e
r
b
o
u
n
d
a
r
y
=
L
o
w
e
r
_
f
e
n
c
e
,
 
u
p
p
e
r
b
o
u
n
d
a
r
y
=
U
p
p
e
r
_
f
e
n
c
e
)
)

```

<pre>
W
i
n
d
S
p
e
e
d
3
p
m
 
o
u
t
l
i
e
r
s
 
a
r
e
 
v
a
l
u
e
s
 
<
 
-
2
0
.
0
 
o
r
 
>
 
5
7
.
0

</pre>
풍
속
3
p
m
(
W
i
n
d
S
p
e
e
d
3
p
m
)
 
변
수
의
 
최
솟
값
과
 
최
댓
값
은
 
각
각
 
0
.
0
과
 
8
7
.
0
입
니
다
.
 
따
라
서
,
 
이
상
치
는
 
5
7
.
0
보
다
 
큰
 
값
입
니
다
.


#
 
*
*
8
.
 
f
e
a
t
u
r
e
 
v
e
c
t
o
r
,
 
목
표
 
변
수
 
선
언
하
기
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
8
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
X
 
=
 
d
f
.
d
r
o
p
(
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
,
 
a
x
i
s
=
1
)


y
 
=
 
d
f
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
```

#
 
*
*
9
.
 
t
r
a
i
n
i
n
g
,
 
t
e
s
t
 
s
e
t
 
으
로
 
분
리
하
기
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
9
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
#
 
s
p
l
i
t
 
X
 
a
n
d
 
y
 
i
n
t
o
 
t
r
a
i
n
i
n
g
 
a
n
d
 
t
e
s
t
i
n
g
 
s
e
t
s


f
r
o
m
 
s
k
l
e
a
r
n
.
m
o
d
e
l
_
s
e
l
e
c
t
i
o
n
 
i
m
p
o
r
t
 
t
r
a
i
n
_
t
e
s
t
_
s
p
l
i
t


X
_
t
r
a
i
n
,
 
X
_
t
e
s
t
,
 
y
_
t
r
a
i
n
,
 
y
_
t
e
s
t
 
=
 
t
r
a
i
n
_
t
e
s
t
_
s
p
l
i
t
(
X
,
 
y
,
 
t
e
s
t
_
s
i
z
e
 
=
 
0
.
2
,
 
r
a
n
d
o
m
_
s
t
a
t
e
 
=
 
0
)

```


```python
#
 
c
h
e
c
k
 
t
h
e
 
s
h
a
p
e
 
o
f
 
X
_
t
r
a
i
n
 
a
n
d
 
X
_
t
e
s
t


X
_
t
r
a
i
n
.
s
h
a
p
e
,
 
X
_
t
e
s
t
.
s
h
a
p
e
```

<pre>
(
(
1
1
6
3
6
8
,
 
2
4
)
,
 
(
2
9
0
9
2
,
 
2
4
)
)
</pre>
#
 
*
*
1
0
.
 
F
e
a
t
u
r
e
 
E
n
g
i
n
e
e
r
i
n
g
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
0
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)






*
*
특
성
 
공
학
(
F
e
a
t
u
r
e
 
E
n
g
i
n
e
e
r
i
n
g
)
*
*
은
 
원
시
 
데
이
터
(
r
a
w
 
d
a
t
a
)
를
 
유
용
한
 
특
성
(
f
e
a
t
u
r
e
)
으
로
 
변
환
하
여
 
모
델
을
 
더
 
잘
 
이
해
하
고
 
예
측
력
을
 
높
이
는
 
과
정
입
니
다
.
 
다
음
으
로
,
 
각
각
의
 
범
주
형
 
변
수
와
 
수
치
형
 
변
수
를
 
다
시
 
나
누
어
 
표
시
하
겠
습
니
다
.



```python
#
 
c
h
e
c
k
 
d
a
t
a
 
t
y
p
e
s
 
i
n
 
X
_
t
r
a
i
n


X
_
t
r
a
i
n
.
d
t
y
p
e
s
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
 
o
b
j
e
c
t

M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
f
l
o
a
t
6
4

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
 
 
o
b
j
e
c
t

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
f
l
o
a
t
6
4

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
 
 
o
b
j
e
c
t

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
 
o
b
j
e
c
t

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
f
l
o
a
t
6
4

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
f
l
o
a
t
6
4

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
f
l
o
a
t
6
4

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
f
l
o
a
t
6
4

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
f
l
o
a
t
6
4

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
f
l
o
a
t
6
4

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
f
l
o
a
t
6
4

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
 
o
b
j
e
c
t

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
6
4

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
6
4

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
6
4

d
t
y
p
e
:
 
o
b
j
e
c
t
</pre>

```python
#
 
d
i
s
p
l
a
y
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


c
a
t
e
g
o
r
i
c
a
l
 
=
 
[
c
o
l
 
f
o
r
 
c
o
l
 
i
n
 
X
_
t
r
a
i
n
.
c
o
l
u
m
n
s
 
i
f
 
X
_
t
r
a
i
n
[
c
o
l
]
.
d
t
y
p
e
s
 
=
=
 
'
O
'
]


c
a
t
e
g
o
r
i
c
a
l
```

<pre>
[
'
L
o
c
a
t
i
o
n
'
,
 
'
W
i
n
d
G
u
s
t
D
i
r
'
,
 
'
W
i
n
d
D
i
r
9
a
m
'
,
 
'
W
i
n
d
D
i
r
3
p
m
'
,
 
'
R
a
i
n
T
o
d
a
y
'
]
</pre>

```python
#
 
d
i
s
p
l
a
y
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s


n
u
m
e
r
i
c
a
l
 
=
 
[
c
o
l
 
f
o
r
 
c
o
l
 
i
n
 
X
_
t
r
a
i
n
.
c
o
l
u
m
n
s
 
i
f
 
X
_
t
r
a
i
n
[
c
o
l
]
.
d
t
y
p
e
s
 
!
=
 
'
O
'
]


n
u
m
e
r
i
c
a
l
```

<pre>
[
'
M
i
n
T
e
m
p
'
,

 
'
M
a
x
T
e
m
p
'
,

 
'
R
a
i
n
f
a
l
l
'
,

 
'
E
v
a
p
o
r
a
t
i
o
n
'
,

 
'
S
u
n
s
h
i
n
e
'
,

 
'
W
i
n
d
G
u
s
t
S
p
e
e
d
'
,

 
'
W
i
n
d
S
p
e
e
d
9
a
m
'
,

 
'
W
i
n
d
S
p
e
e
d
3
p
m
'
,

 
'
H
u
m
i
d
i
t
y
9
a
m
'
,

 
'
H
u
m
i
d
i
t
y
3
p
m
'
,

 
'
P
r
e
s
s
u
r
e
9
a
m
'
,

 
'
P
r
e
s
s
u
r
e
3
p
m
'
,

 
'
C
l
o
u
d
9
a
m
'
,

 
'
C
l
o
u
d
3
p
m
'
,

 
'
T
e
m
p
9
a
m
'
,

 
'
T
e
m
p
3
p
m
'
,

 
'
Y
e
a
r
'
,

 
'
M
o
n
t
h
'
,

 
'
D
a
y
'
]
</pre>
#
#
#
 
E
n
g
i
n
e
e
r
i
n
g
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s







```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
X
_
t
r
a
i
n


X
_
t
r
a
i
n
[
n
u
m
e
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
 
1
1
8
3

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
 
1
0
1
9

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
 
2
6
1
7

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
5
0
3
5
5

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
5
5
8
9
9

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
 
8
2
1
8

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
 
1
4
0
9

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
 
2
4
5
6

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
 
2
1
4
7

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
 
3
5
9
8

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
1
2
0
9
1

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
1
2
0
6
4

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
4
4
7
9
6

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
4
7
5
5
7

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
 
1
4
1
5

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
 
2
8
6
5

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
X
_
t
e
s
t


X
_
t
e
s
t
[
n
u
m
e
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
 
 
3
0
2

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
 
 
2
4
2

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
 
 
6
4
4

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
1
2
4
3
5

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
1
3
9
3
6

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
 
2
0
4
5

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
 
 
3
5
8

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
 
 
6
0
6

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
 
 
5
0
7

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
 
 
9
0
9

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
 
2
9
7
4

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
 
2
9
6
4

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
1
1
0
9
2

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
1
1
8
0
1

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
 
 
3
5
2

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
 
 
7
4
4

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
p
r
i
n
t
 
p
e
r
c
e
n
t
a
g
e
 
o
f
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
t
h
e
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
t
r
a
i
n
i
n
g
 
s
e
t


f
o
r
 
c
o
l
 
i
n
 
n
u
m
e
r
i
c
a
l
:

 
 
 
 
i
f
 
X
_
t
r
a
i
n
[
c
o
l
]
.
i
s
n
u
l
l
(
)
.
m
e
a
n
(
)
>
0
:

 
 
 
 
 
 
 
 
p
r
i
n
t
(
c
o
l
,
 
r
o
u
n
d
(
X
_
t
r
a
i
n
[
c
o
l
]
.
i
s
n
u
l
l
(
)
.
m
e
a
n
(
)
,
4
)
)
```

<pre>
M
i
n
T
e
m
p
 
0
.
0
1
0
2

M
a
x
T
e
m
p
 
0
.
0
0
8
8

R
a
i
n
f
a
l
l
 
0
.
0
2
2
5

E
v
a
p
o
r
a
t
i
o
n
 
0
.
4
3
2
7

S
u
n
s
h
i
n
e
 
0
.
4
8
0
4

W
i
n
d
G
u
s
t
S
p
e
e
d
 
0
.
0
7
0
6

W
i
n
d
S
p
e
e
d
9
a
m
 
0
.
0
1
2
1

W
i
n
d
S
p
e
e
d
3
p
m
 
0
.
0
2
1
1

H
u
m
i
d
i
t
y
9
a
m
 
0
.
0
1
8
5

H
u
m
i
d
i
t
y
3
p
m
 
0
.
0
3
0
9

P
r
e
s
s
u
r
e
9
a
m
 
0
.
1
0
3
9

P
r
e
s
s
u
r
e
3
p
m
 
0
.
1
0
3
7

C
l
o
u
d
9
a
m
 
0
.
3
8
5

C
l
o
u
d
3
p
m
 
0
.
4
0
8
7

T
e
m
p
9
a
m
 
0
.
0
1
2
2

T
e
m
p
3
p
m
 
0
.
0
2
4
6

</pre>
#
#
#
 
A
s
s
u
m
p
t
i
o
n






I
 
a
s
s
u
m
e
 
t
h
a
t
 
t
h
e
 
d
a
t
a
 
a
r
e
 
m
i
s
s
i
n
g
 
c
o
m
p
l
e
t
e
l
y
 
a
t
 
r
a
n
d
o
m
 
(
M
C
A
R
)
.
 
T
h
e
r
e
 
a
r
e
 
t
w
o
 
m
e
t
h
o
d
s
 
w
h
i
c
h
 
c
a
n
 
b
e
 
u
s
e
d
 
t
o
 
i
m
p
u
t
e
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
.
 
O
n
e
 
i
s
 
m
e
a
n
 
o
r
 
m
e
d
i
a
n
 
i
m
p
u
t
a
t
i
o
n
 
a
n
d
 
o
t
h
e
r
 
o
n
e
 
i
s
 
r
a
n
d
o
m
 
s
a
m
p
l
e
 
i
m
p
u
t
a
t
i
o
n
.
 
W
h
e
n
 
t
h
e
r
e
 
a
r
e
 
o
u
t
l
i
e
r
s
 
i
n
 
t
h
e
 
d
a
t
a
s
e
t
,
 
w
e
 
s
h
o
u
l
d
 
u
s
e
 
m
e
d
i
a
n
 
i
m
p
u
t
a
t
i
o
n
.
 
S
o
,
 
I
 
w
i
l
l
 
u
s
e
 
m
e
d
i
a
n
 
i
m
p
u
t
a
t
i
o
n
 
b
e
c
a
u
s
e
 
m
e
d
i
a
n
 
i
m
p
u
t
a
t
i
o
n
 
i
s
 
r
o
b
u
s
t
 
t
o
 
o
u
t
l
i
e
r
s
.






I
 
w
i
l
l
 
i
m
p
u
t
e
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
w
i
t
h
 
t
h
e
 
a
p
p
r
o
p
r
i
a
t
e
 
s
t
a
t
i
s
t
i
c
a
l
 
m
e
a
s
u
r
e
s
 
o
f
 
t
h
e
 
d
a
t
a
,
 
i
n
 
t
h
i
s
 
c
a
s
e
 
m
e
d
i
a
n
.
 
I
m
p
u
t
a
t
i
o
n
 
s
h
o
u
l
d
 
b
e
 
d
o
n
e
 
o
v
e
r
 
t
h
e
 
t
r
a
i
n
i
n
g
 
s
e
t
,
 
a
n
d
 
t
h
e
n
 
p
r
o
p
a
g
a
t
e
d
 
t
o
 
t
h
e
 
t
e
s
t
 
s
e
t
.
 
I
t
 
m
e
a
n
s
 
t
h
a
t
 
t
h
e
 
s
t
a
t
i
s
t
i
c
a
l
 
m
e
a
s
u
r
e
s
 
t
o
 
b
e
 
u
s
e
d
 
t
o
 
f
i
l
l
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
b
o
t
h
 
i
n
 
t
r
a
i
n
 
a
n
d
 
t
e
s
t
 
s
e
t
,
 
s
h
o
u
l
d
 
b
e
 
e
x
t
r
a
c
t
e
d
 
f
r
o
m
 
t
h
e
 
t
r
a
i
n
 
s
e
t
 
o
n
l
y
.
 
T
h
i
s
 
i
s
 
t
o
 
a
v
o
i
d
 
o
v
e
r
f
i
t
t
i
n
g
.



```python
#
 
i
m
p
u
t
e
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
X
_
t
r
a
i
n
 
a
n
d
 
X
_
t
e
s
t
 
w
i
t
h
 
r
e
s
p
e
c
t
i
v
e
 
c
o
l
u
m
n
 
m
e
d
i
a
n
 
i
n
 
X
_
t
r
a
i
n


f
o
r
 
d
f
1
 
i
n
 
[
X
_
t
r
a
i
n
,
 
X
_
t
e
s
t
]
:

 
 
 
 
f
o
r
 
c
o
l
 
i
n
 
n
u
m
e
r
i
c
a
l
:

 
 
 
 
 
 
 
 
c
o
l
_
m
e
d
i
a
n
=
X
_
t
r
a
i
n
[
c
o
l
]
.
m
e
d
i
a
n
(
)

 
 
 
 
 
 
 
 
d
f
1
[
c
o
l
]
.
f
i
l
l
n
a
(
c
o
l
_
m
e
d
i
a
n
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)
 
 
 
 
 
 
 
 
 
 
 

 
 
 
 
 
 
```


```python
#
 
c
h
e
c
k
 
a
g
a
i
n
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
X
_
t
r
a
i
n


X
_
t
r
a
i
n
[
n
u
m
e
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
0

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
0

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
0

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
0

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
0

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
0

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
0

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
0

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
0

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
0

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
0

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
n
u
m
e
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
X
_
t
e
s
t


X
_
t
e
s
t
[
n
u
m
e
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
0

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
0

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
0

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
0

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
0

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
0

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
0

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
0

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
0

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
0

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
0

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
N
o
w
,
 
w
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
r
e
 
a
r
e
 
n
o
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
t
h
e
 
n
u
m
e
r
i
c
a
l
 
c
o
l
u
m
n
s
 
o
f
 
t
r
a
i
n
i
n
g
 
a
n
d
 
t
e
s
t
 
s
e
t
.


#
#
#
 
E
n
g
i
n
e
e
r
i
n
g
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s



```python
#
 
p
r
i
n
t
 
p
e
r
c
e
n
t
a
g
e
 
o
f
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
t
h
e
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
t
r
a
i
n
i
n
g
 
s
e
t


X
_
t
r
a
i
n
[
c
a
t
e
g
o
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
m
e
a
n
(
)
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
0
.
0
7
1
0
6
8

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
0
.
0
7
2
5
9
7

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
0
.
0
2
8
9
5
1

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
0
.
0
2
2
4
8
9

d
t
y
p
e
:
 
f
l
o
a
t
6
4
</pre>

```python
#
 
p
r
i
n
t
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
w
i
t
h
 
m
i
s
s
i
n
g
 
d
a
t
a


f
o
r
 
c
o
l
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
:

 
 
 
 
i
f
 
X
_
t
r
a
i
n
[
c
o
l
]
.
i
s
n
u
l
l
(
)
.
m
e
a
n
(
)
>
0
:

 
 
 
 
 
 
 
 
p
r
i
n
t
(
c
o
l
,
 
(
X
_
t
r
a
i
n
[
c
o
l
]
.
i
s
n
u
l
l
(
)
.
m
e
a
n
(
)
)
)
```

<pre>
W
i
n
d
G
u
s
t
D
i
r
 
0
.
0
7
1
0
6
7
6
4
7
4
6
3
2
2
0
1
3

W
i
n
d
D
i
r
9
a
m
 
0
.
0
7
2
5
9
7
2
7
7
6
0
2
0
8
9
9
2

W
i
n
d
D
i
r
3
p
m
 
0
.
0
2
8
9
5
1
2
5
8
0
7
7
8
2
2
0
8
3

R
a
i
n
T
o
d
a
y
 
0
.
0
2
2
4
8
9
0
0
0
4
1
2
4
8
4
5
3

</pre>

```python
#
 
i
m
p
u
t
e
 
m
i
s
s
i
n
g
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
w
i
t
h
 
m
o
s
t
 
f
r
e
q
u
e
n
t
 
v
a
l
u
e


f
o
r
 
d
f
2
 
i
n
 
[
X
_
t
r
a
i
n
,
 
X
_
t
e
s
t
]
:

 
 
 
 
d
f
2
[
'
W
i
n
d
G
u
s
t
D
i
r
'
]
.
f
i
l
l
n
a
(
X
_
t
r
a
i
n
[
'
W
i
n
d
G
u
s
t
D
i
r
'
]
.
m
o
d
e
(
)
[
0
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)

 
 
 
 
d
f
2
[
'
W
i
n
d
D
i
r
9
a
m
'
]
.
f
i
l
l
n
a
(
X
_
t
r
a
i
n
[
'
W
i
n
d
D
i
r
9
a
m
'
]
.
m
o
d
e
(
)
[
0
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)

 
 
 
 
d
f
2
[
'
W
i
n
d
D
i
r
3
p
m
'
]
.
f
i
l
l
n
a
(
X
_
t
r
a
i
n
[
'
W
i
n
d
D
i
r
3
p
m
'
]
.
m
o
d
e
(
)
[
0
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)

 
 
 
 
d
f
2
[
'
R
a
i
n
T
o
d
a
y
'
]
.
f
i
l
l
n
a
(
X
_
t
r
a
i
n
[
'
R
a
i
n
T
o
d
a
y
'
]
.
m
o
d
e
(
)
[
0
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)
```


```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
X
_
t
r
a
i
n


X
_
t
r
a
i
n
[
c
a
t
e
g
o
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
0

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
0

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
0

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s
 
i
n
 
X
_
t
e
s
t


X
_
t
e
s
t
[
c
a
t
e
g
o
r
i
c
a
l
]
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
0

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
0

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
0

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
A
s
 
a
 
f
i
n
a
l
 
c
h
e
c
k
,
 
I
 
w
i
l
l
 
c
h
e
c
k
 
f
o
r
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
X
_
t
r
a
i
n
 
a
n
d
 
X
_
t
e
s
t
.



```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
X
_
t
r
a
i
n


X
_
t
r
a
i
n
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
0

M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
0

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
0

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
0

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
 
0

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
0

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
0

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
0

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
0

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
0

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
0

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
0

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
0

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
0

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
0

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>

```python
#
 
c
h
e
c
k
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
X
_
t
e
s
t


X
_
t
e
s
t
.
i
s
n
u
l
l
(
)
.
s
u
m
(
)
```

<pre>
L
o
c
a
t
i
o
n
 
 
 
 
 
 
 
 
 
0

M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

M
a
x
T
e
m
p
 
 
 
 
 
 
 
 
 
 
0

R
a
i
n
f
a
l
l
 
 
 
 
 
 
 
 
 
0

E
v
a
p
o
r
a
t
i
o
n
 
 
 
 
 
 
0

S
u
n
s
h
i
n
e
 
 
 
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
D
i
r
 
 
 
 
 
 
0

W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
 
0

W
i
n
d
D
i
r
9
a
m
 
 
 
 
 
 
 
0

W
i
n
d
D
i
r
3
p
m
 
 
 
 
 
 
 
0

W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
 
 
0

W
i
n
d
S
p
e
e
d
3
p
m
 
 
 
 
 
0

H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
 
 
0

H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
 
 
0

P
r
e
s
s
u
r
e
3
p
m
 
 
 
 
 
 
0

C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
 
 
0

C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
 
0

T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
 
 
0

T
e
m
p
3
p
m
 
 
 
 
 
 
 
 
 
 
0

R
a
i
n
T
o
d
a
y
 
 
 
 
 
 
 
 
0

Y
e
a
r
 
 
 
 
 
 
 
 
 
 
 
 
 
0

M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
0

D
a
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0

d
t
y
p
e
:
 
i
n
t
6
4
</pre>
W
e
 
c
a
n
 
s
e
e
 
t
h
a
t
 
t
h
e
r
e
 
a
r
e
 
n
o
 
m
i
s
s
i
n
g
 
v
a
l
u
e
s
 
i
n
 
X
_
t
r
a
i
n
 
a
n
d
 
X
_
t
e
s
t
.


#
#
#
 
수
치
형
 
변
수
에
서
 
이
상
치
(
O
u
t
l
i
e
r
)
 
다
루
기


`
강
수
량
(
R
a
i
n
f
a
l
l
)
,
 
증
발
량
(
E
v
a
p
o
r
a
t
i
o
n
)
,
 
풍
속
9
a
m
(
W
i
n
d
S
p
e
e
d
9
a
m
)
,
 
풍
속
3
p
m
(
W
i
n
d
S
p
e
e
d
3
p
m
)
`
 
열
에
 
이
상
치
가
 
있
음
을
 
확
인
했
습
니
다
.
 
위
 
변
수
들
에
서
 
최
댓
값
을
 
상
한
선
으
로
 
설
정
하
고
 
이
상
치
를
 
제
거
하
기
 
위
해
 
T
o
p
-
c
o
d
i
n
g
 
접
근
법
(
T
o
p
-
c
o
d
i
n
g
 
a
p
p
r
o
a
c
h
)
을
 
사
용
하
겠
습
니
다
.



```python
d
e
f
 
m
a
x
_
v
a
l
u
e
(
d
f
3
,
 
v
a
r
i
a
b
l
e
,
 
t
o
p
)
:

 
 
 
 
r
e
t
u
r
n
 
n
p
.
w
h
e
r
e
(
d
f
3
[
v
a
r
i
a
b
l
e
]
>
t
o
p
,
 
t
o
p
,
 
d
f
3
[
v
a
r
i
a
b
l
e
]
)


f
o
r
 
d
f
3
 
i
n
 
[
X
_
t
r
a
i
n
,
 
X
_
t
e
s
t
]
:

 
 
 
 
d
f
3
[
'
R
a
i
n
f
a
l
l
'
]
 
=
 
m
a
x
_
v
a
l
u
e
(
d
f
3
,
 
'
R
a
i
n
f
a
l
l
'
,
 
3
.
2
)

 
 
 
 
d
f
3
[
'
E
v
a
p
o
r
a
t
i
o
n
'
]
 
=
 
m
a
x
_
v
a
l
u
e
(
d
f
3
,
 
'
E
v
a
p
o
r
a
t
i
o
n
'
,
 
2
1
.
8
)

 
 
 
 
d
f
3
[
'
W
i
n
d
S
p
e
e
d
9
a
m
'
]
 
=
 
m
a
x
_
v
a
l
u
e
(
d
f
3
,
 
'
W
i
n
d
S
p
e
e
d
9
a
m
'
,
 
5
5
)

 
 
 
 
d
f
3
[
'
W
i
n
d
S
p
e
e
d
3
p
m
'
]
 
=
 
m
a
x
_
v
a
l
u
e
(
d
f
3
,
 
'
W
i
n
d
S
p
e
e
d
3
p
m
'
,
 
5
7
)
```


```python
X
_
t
r
a
i
n
.
R
a
i
n
f
a
l
l
.
m
a
x
(
)
,
 
X
_
t
e
s
t
.
R
a
i
n
f
a
l
l
.
m
a
x
(
)
```

<pre>
(
3
.
2
,
 
3
.
2
)
</pre>

```python
X
_
t
r
a
i
n
.
E
v
a
p
o
r
a
t
i
o
n
.
m
a
x
(
)
,
 
X
_
t
e
s
t
.
E
v
a
p
o
r
a
t
i
o
n
.
m
a
x
(
)
```

<pre>
(
2
1
.
8
,
 
2
1
.
8
)
</pre>

```python
X
_
t
r
a
i
n
.
W
i
n
d
S
p
e
e
d
9
a
m
.
m
a
x
(
)
,
 
X
_
t
e
s
t
.
W
i
n
d
S
p
e
e
d
9
a
m
.
m
a
x
(
)
```

<pre>
(
5
5
.
0
,
 
5
5
.
0
)
</pre>

```python
X
_
t
r
a
i
n
.
W
i
n
d
S
p
e
e
d
3
p
m
.
m
a
x
(
)
,
 
X
_
t
e
s
t
.
W
i
n
d
S
p
e
e
d
3
p
m
.
m
a
x
(
)
```

<pre>
(
5
7
.
0
,
 
5
7
.
0
)
</pre>

```python
X
_
t
r
a
i
n
[
n
u
m
e
r
i
c
a
l
]
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
M
a
x
T
e
m
p
 
 
 
 
 
 
 
R
a
i
n
f
a
l
l
 
 
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
1
2
.
1
9
0
1
8
9
 
 
 
 
 
 
2
3
.
2
0
3
1
0
7
 
 
 
 
 
 
 
0
.
6
7
0
8
0
0
 
 
 
 
 
 
 
5
.
0
9
3
3
6
2
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
6
.
3
6
6
8
9
3
 
 
 
 
 
 
 
7
.
0
8
5
4
0
8
 
 
 
 
 
 
 
1
.
1
8
1
5
1
2
 
 
 
 
 
 
 
2
.
8
0
0
2
0
0
 
 
 

m
i
n
 
 
 
 
 
 
 
 
-
8
.
5
0
0
0
0
0
 
 
 
 
 
 
-
4
.
8
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
7
.
7
0
0
0
0
0
 
 
 
 
 
 
1
8
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
4
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
1
2
.
0
0
0
0
0
0
 
 
 
 
 
 
2
2
.
6
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
4
.
7
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
1
6
.
8
0
0
0
0
0
 
 
 
 
 
 
2
8
.
2
0
0
0
0
0
 
 
 
 
 
 
 
0
.
6
0
0
0
0
0
 
 
 
 
 
 
 
5
.
2
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
3
1
.
9
0
0
0
0
0
 
 
 
 
 
 
4
8
.
1
0
0
0
0
0
 
 
 
 
 
 
 
3
.
2
0
0
0
0
0
 
 
 
 
 
 
2
1
.
8
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
7
.
9
8
2
4
7
6
 
 
 
 
 
 
3
9
.
9
8
2
0
9
1
 
 
 
 
 
 
1
4
.
0
2
9
3
8
1
 
 
 
 
 
 
1
8
.
6
8
7
4
6
6
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
7
6
1
6
3
9
 
 
 
 
 
 
1
3
.
1
2
7
9
5
3
 
 
 
 
 
 
 
8
.
8
3
5
5
9
6
 
 
 
 
 
 
 
8
.
7
0
0
6
1
8
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
6
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
8
.
2
0
0
0
0
0
 
 
 
 
 
 
3
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
7
.
0
0
0
0
0
0
 
 
 
 
 
 
1
3
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
8
.
4
0
0
0
0
0
 
 
 
 
 
 
3
9
.
0
0
0
0
0
0
 
 
 
 
 
 
1
3
.
0
0
0
0
0
0
 
 
 
 
 
 
1
9
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
8
.
6
0
0
0
0
0
 
 
 
 
 
 
4
6
.
0
0
0
0
0
0
 
 
 
 
 
 
1
9
.
0
0
0
0
0
0
 
 
 
 
 
 
2
4
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
1
4
.
5
0
0
0
0
0
 
 
 
 
 
1
3
5
.
0
0
0
0
0
0
 
 
 
 
 
 
5
5
.
0
0
0
0
0
0
 
 
 
 
 
 
5
7
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
 
 
P
r
e
s
s
u
r
e
9
a
m
 
 
 
 
P
r
e
s
s
u
r
e
3
p
m
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
6
8
.
9
5
0
6
9
1
 
 
 
 
 
 
5
1
.
6
0
5
8
2
8
 
 
 
 
1
0
1
7
.
6
3
9
8
9
1
 
 
 
 
1
0
1
5
.
2
4
4
9
4
6
 
 
 

s
t
d
 
 
 
 
 
 
 
 
1
8
.
8
1
1
4
3
7
 
 
 
 
 
 
2
0
.
4
3
9
9
9
9
 
 
 
 
 
 
 
6
.
7
2
8
2
3
4
 
 
 
 
 
 
 
6
.
6
6
1
5
1
7
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
9
8
0
.
5
0
0
0
0
0
 
 
 
 
 
9
7
7
.
1
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
5
7
.
0
0
0
0
0
0
 
 
 
 
 
 
3
7
.
0
0
0
0
0
0
 
 
 
 
1
0
1
3
.
5
0
0
0
0
0
 
 
 
 
1
0
1
1
.
1
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
7
0
.
0
0
0
0
0
0
 
 
 
 
 
 
5
2
.
0
0
0
0
0
0
 
 
 
 
1
0
1
7
.
6
0
0
0
0
0
 
 
 
 
1
0
1
5
.
2
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
8
3
.
0
0
0
0
0
0
 
 
 
 
 
 
6
5
.
0
0
0
0
0
0
 
 
 
 
1
0
2
1
.
8
0
0
0
0
0
 
 
 
 
1
0
1
9
.
4
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
1
0
0
.
0
0
0
0
0
0
 
 
 
 
 
1
0
0
.
0
0
0
0
0
0
 
 
 
 
1
0
4
1
.
0
0
0
0
0
0
 
 
 
 
1
0
3
9
.
6
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
C
l
o
u
d
9
a
m
 
 
 
 
 
 
 
C
l
o
u
d
3
p
m
 
 
 
 
 
 
 
 
T
e
m
p
9
a
m
 
 
 
 
 
 
 
 
T
e
m
p
3
p
m
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
4
.
6
6
4
0
9
2
 
 
 
 
 
 
 
4
.
7
1
0
7
2
8
 
 
 
 
 
 
1
6
.
9
7
9
4
5
4
 
 
 
 
 
 
2
1
.
6
5
7
1
9
5
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
2
8
0
6
8
7
 
 
 
 
 
 
 
2
.
1
0
6
0
4
0
 
 
 
 
 
 
 
6
.
4
4
9
6
4
1
 
 
 
 
 
 
 
6
.
8
4
8
2
9
3
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
-
7
.
2
0
0
0
0
0
 
 
 
 
 
 
-
5
.
4
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
3
.
0
0
0
0
0
0
 
 
 
 
 
 
 
4
.
0
0
0
0
0
0
 
 
 
 
 
 
1
2
.
3
0
0
0
0
0
 
 
 
 
 
 
1
6
.
7
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
5
.
0
0
0
0
0
0
 
 
 
 
 
 
 
5
.
0
0
0
0
0
0
 
 
 
 
 
 
1
6
.
7
0
0
0
0
0
 
 
 
 
 
 
2
1
.
1
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
6
.
0
0
0
0
0
0
 
 
 
 
 
 
 
6
.
0
0
0
0
0
0
 
 
 
 
 
 
2
1
.
5
0
0
0
0
0
 
 
 
 
 
 
2
6
.
2
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
9
.
0
0
0
0
0
0
 
 
 
 
 
 
 
8
.
0
0
0
0
0
0
 
 
 
 
 
 
4
0
.
2
0
0
0
0
0
 
 
 
 
 
 
4
6
.
7
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
Y
e
a
r
 
 
 
 
 
 
 
 
 
 
M
o
n
t
h
 
 
 
 
 
 
 
 
 
 
 
 
D
a
y
 
 

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 

m
e
a
n
 
 
 
 
 
2
0
1
2
.
7
6
7
0
5
8
 
 
 
 
 
 
 
6
.
3
9
5
0
9
1
 
 
 
 
 
 
1
5
.
7
3
1
9
5
4
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
5
3
8
4
0
1
 
 
 
 
 
 
 
3
.
4
2
5
4
5
1
 
 
 
 
 
 
 
8
.
7
9
6
9
3
1
 
 

m
i
n
 
 
 
 
 
 
2
0
0
7
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 

2
5
%
 
 
 
 
 
 
2
0
1
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
3
.
0
0
0
0
0
0
 
 
 
 
 
 
 
8
.
0
0
0
0
0
0
 
 

5
0
%
 
 
 
 
 
 
2
0
1
3
.
0
0
0
0
0
0
 
 
 
 
 
 
 
6
.
0
0
0
0
0
0
 
 
 
 
 
 
1
6
.
0
0
0
0
0
0
 
 

7
5
%
 
 
 
 
 
 
2
0
1
5
.
0
0
0
0
0
0
 
 
 
 
 
 
 
9
.
0
0
0
0
0
0
 
 
 
 
 
 
2
3
.
0
0
0
0
0
0
 
 

m
a
x
 
 
 
 
 
 
2
0
1
7
.
0
0
0
0
0
0
 
 
 
 
 
 
1
2
.
0
0
0
0
0
0
 
 
 
 
 
 
3
1
.
0
0
0
0
0
0
 
 
</pre>
이
제
 
`
R
a
i
n
f
a
l
l
,
 
E
v
a
p
o
r
a
t
i
o
n
,
 
W
i
n
d
S
p
e
e
d
9
a
m
,
 
W
i
n
d
S
p
e
e
d
3
p
m
`
 
열
에
서
 
발
견
되
었
던
 
이
상
치
(
o
u
t
l
i
e
r
s
)
들
이
 
잘
린
 
것
을
 
확
인
할
 
수
 
있
습
니
다
.


#
#
#
 
E
n
c
o
d
e
 
c
a
t
e
g
o
r
i
c
a
l
 
v
a
r
i
a
b
l
e
s



```python
c
a
t
e
g
o
r
i
c
a
l
```

<pre>
[
'
L
o
c
a
t
i
o
n
'
,
 
'
W
i
n
d
G
u
s
t
D
i
r
'
,
 
'
W
i
n
d
D
i
r
9
a
m
'
,
 
'
W
i
n
d
D
i
r
3
p
m
'
,
 
'
R
a
i
n
T
o
d
a
y
'
]
</pre>

```python
X
_
t
r
a
i
n
[
c
a
t
e
g
o
r
i
c
a
l
]
.
h
e
a
d
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
L
o
c
a
t
i
o
n
 
W
i
n
d
G
u
s
t
D
i
r
 
W
i
n
d
D
i
r
9
a
m
 
W
i
n
d
D
i
r
3
p
m
 
R
a
i
n
T
o
d
a
y

2
2
9
2
6
 
 
 
N
o
r
f
o
l
k
I
s
l
a
n
d
 
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
N
o

8
0
7
3
5
 
 
 
 
 
 
 
 
W
a
t
s
o
n
i
a
 
 
 
 
 
 
 
 
 
 
N
E
 
 
 
 
 
 
 
 
N
N
W
 
 
 
 
 
 
 
 
N
N
E
 
 
 
 
 
 
 
 
N
o

1
2
1
7
6
4
 
 
 
 
 
 
 
 
 
 
P
e
r
t
h
 
 
 
 
 
 
 
 
 
 
S
W
 
 
 
 
 
 
 
 
 
 
N
 
 
 
 
 
 
 
 
 
S
W
 
 
 
 
 
 
 
Y
e
s

1
3
9
8
2
1
 
 
 
 
 
 
 
 
 
D
a
r
w
i
n
 
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
 
 
E
 
 
 
 
 
 
 
 
N
o

1
8
6
7
 
 
 
 
 
 
 
 
 
 
 
A
l
b
u
r
y
 
 
 
 
 
 
 
 
 
 
 
E
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
 
 
E
 
 
 
 
 
 
 
Y
e
s
</pre>

```python
#
 
e
n
c
o
d
e
 
R
a
i
n
T
o
d
a
y
 
v
a
r
i
a
b
l
e


i
m
p
o
r
t
 
c
a
t
e
g
o
r
y
_
e
n
c
o
d
e
r
s
 
a
s
 
c
e


e
n
c
o
d
e
r
 
=
 
c
e
.
B
i
n
a
r
y
E
n
c
o
d
e
r
(
c
o
l
s
=
[
'
R
a
i
n
T
o
d
a
y
'
]
)


X
_
t
r
a
i
n
 
=
 
e
n
c
o
d
e
r
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
X
_
t
r
a
i
n
)


X
_
t
e
s
t
 
=
 
e
n
c
o
d
e
r
.
t
r
a
n
s
f
o
r
m
(
X
_
t
e
s
t
)
```


```python
X
_
t
r
a
i
n
.
h
e
a
d
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
L
o
c
a
t
i
o
n
 
 
M
i
n
T
e
m
p
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
 
\

2
2
9
2
6
 
 
 
N
o
r
f
o
l
k
I
s
l
a
n
d
 
 
 
 
 
1
8
.
8
 
 
 
 
 
2
3
.
7
 
 
 
 
 
 
 
0
.
2
 
 
 
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
7
.
3
 
 
 

8
0
7
3
5
 
 
 
 
 
 
 
 
W
a
t
s
o
n
i
a
 
 
 
 
 
 
9
.
3
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
0
.
2
 
 
 
 
 
 
 
 
 
 
1
.
6
 
 
 
 
 
 
1
0
.
9
 
 
 

1
2
1
7
6
4
 
 
 
 
 
 
 
 
 
 
P
e
r
t
h
 
 
 
 
 
1
0
.
9
 
 
 
 
 
2
2
.
2
 
 
 
 
 
 
 
1
.
4
 
 
 
 
 
 
 
 
 
 
1
.
2
 
 
 
 
 
 
 
9
.
6
 
 
 

1
3
9
8
2
1
 
 
 
 
 
 
 
 
 
D
a
r
w
i
n
 
 
 
 
 
1
9
.
3
 
 
 
 
 
2
9
.
9
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
9
.
2
 
 
 
 
 
 
1
1
.
0
 
 
 

1
8
6
7
 
 
 
 
 
 
 
 
 
 
 
A
l
b
u
r
y
 
 
 
 
 
1
5
.
7
 
 
 
 
 
1
7
.
6
 
 
 
 
 
 
 
3
.
2
 
 
 
 
 
 
 
 
 
 
4
.
7
 
 
 
 
 
 
 
8
.
4
 
 
 


 
 
 
 
 
 
 
W
i
n
d
G
u
s
t
D
i
r
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
W
i
n
d
D
i
r
9
a
m
 
W
i
n
d
D
i
r
3
p
m
 
 
.
.
.
 
 
P
r
e
s
s
u
r
e
3
p
m
 
 
\

2
2
9
2
6
 
 
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
 
 
 
5
2
.
0
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
E
S
E
 
 
.
.
.
 
 
 
 
 
 
 
1
0
1
3
.
9
 
 
 

8
0
7
3
5
 
 
 
 
 
 
 
 
 
 
 
N
E
 
 
 
 
 
 
 
 
 
 
 
4
8
.
0
 
 
 
 
 
 
 
 
N
N
W
 
 
 
 
 
 
 
 
N
N
E
 
 
.
.
.
 
 
 
 
 
 
 
1
0
1
4
.
6
 
 
 

1
2
1
7
6
4
 
 
 
 
 
 
 
 
 
 
S
W
 
 
 
 
 
 
 
 
 
 
 
2
6
.
0
 
 
 
 
 
 
 
 
 
 
N
 
 
 
 
 
 
 
 
 
S
W
 
 
.
.
.
 
 
 
 
 
 
 
1
0
1
4
.
9
 
 
 

1
3
9
8
2
1
 
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
 
 
 
4
3
.
0
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
 
 
E
 
 
.
.
.
 
 
 
 
 
 
 
1
0
1
2
.
1
 
 
 

1
8
6
7
 
 
 
 
 
 
 
 
 
 
 
 
 
E
 
 
 
 
 
 
 
 
 
 
 
2
0
.
0
 
 
 
 
 
 
 
 
E
S
E
 
 
 
 
 
 
 
 
 
 
E
 
 
.
.
.
 
 
 
 
 
 
 
1
0
1
0
.
5
 
 
 


 
 
 
 
 
 
 
 
C
l
o
u
d
9
a
m
 
 
C
l
o
u
d
3
p
m
 
 
T
e
m
p
9
a
m
 
 
T
e
m
p
3
p
m
 
 
R
a
i
n
T
o
d
a
y
_
0
 
 
R
a
i
n
T
o
d
a
y
_
1
 
 
Y
e
a
r
 
 
\

2
2
9
2
6
 
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
2
1
.
4
 
 
 
 
 
2
2
.
2
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
2
0
1
4
 
 
 

8
0
7
3
5
 
 
 
 
 
 
 
 
3
.
0
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
1
4
.
3
 
 
 
 
 
2
3
.
2
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
2
0
1
6
 
 
 

1
2
1
7
6
4
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
1
6
.
6
 
 
 
 
 
2
1
.
5
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
2
0
1
1
 
 
 

1
3
9
8
2
1
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
2
3
.
2
 
 
 
 
 
2
9
.
1
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
2
0
1
0
 
 
 

1
8
6
7
 
 
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
 
 
8
.
0
 
 
 
 
 
1
6
.
5
 
 
 
 
 
1
7
.
3
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
2
0
1
4
 
 
 


 
 
 
 
 
 
 
 
M
o
n
t
h
 
 
D
a
y
 
 

2
2
9
2
6
 
 
 
 
 
 
 
3
 
 
 
1
2
 
 

8
0
7
3
5
 
 
 
 
 
 
1
0
 
 
 
 
6
 
 

1
2
1
7
6
4
 
 
 
 
 
 
8
 
 
 
3
1
 
 

1
3
9
8
2
1
 
 
 
 
 
 
6
 
 
 
1
1
 
 

1
8
6
7
 
 
 
 
 
 
 
 
4
 
 
 
1
0
 
 


[
5
 
r
o
w
s
 
x
 
2
5
 
c
o
l
u
m
n
s
]
</pre>
R
a
i
n
T
o
d
a
y
 
변
수
에
서
 
두
 
가
지
 
추
가
 
변
수
 
`
R
a
i
n
T
o
d
a
y
_
0
`
 
및
 
`
R
a
i
n
T
o
d
a
y
_
1
`
이
 
생
성
된
 
것
을
 
확
인
할
 
수
 
있
습
니
다
.




이
제
 
X
_
t
r
a
i
n
 
훈
련
 
세
트
를
 
만
들
어
 
보
겠
습
니
다
.



```python
X
_
t
r
a
i
n
 
=
 
p
d
.
c
o
n
c
a
t
(
[
X
_
t
r
a
i
n
[
n
u
m
e
r
i
c
a
l
]
,
 
X
_
t
r
a
i
n
[
[
'
R
a
i
n
T
o
d
a
y
_
0
'
,
 
'
R
a
i
n
T
o
d
a
y
_
1
'
]
]
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
r
a
i
n
.
L
o
c
a
t
i
o
n
)
,
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
r
a
i
n
.
W
i
n
d
G
u
s
t
D
i
r
)
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
r
a
i
n
.
W
i
n
d
D
i
r
9
a
m
)
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
r
a
i
n
.
W
i
n
d
D
i
r
3
p
m
)
]
,
 
a
x
i
s
=
1
)
```


```python
X
_
t
r
a
i
n
.
h
e
a
d
(
)
```

<pre>
 
 
 
 
 
 
 
 
M
i
n
T
e
m
p
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
\

2
2
9
2
6
 
 
 
 
 
 
1
8
.
8
 
 
 
 
 
2
3
.
7
 
 
 
 
 
 
 
0
.
2
 
 
 
 
 
 
 
 
 
 
5
.
0
 
 
 
 
 
 
 
7
.
3
 
 
 
 
 
 
 
 
 
 
 
5
2
.
0
 
 
 

8
0
7
3
5
 
 
 
 
 
 
 
9
.
3
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
0
.
2
 
 
 
 
 
 
 
 
 
 
1
.
6
 
 
 
 
 
 
1
0
.
9
 
 
 
 
 
 
 
 
 
 
 
4
8
.
0
 
 
 

1
2
1
7
6
4
 
 
 
 
 
1
0
.
9
 
 
 
 
 
2
2
.
2
 
 
 
 
 
 
 
1
.
4
 
 
 
 
 
 
 
 
 
 
1
.
2
 
 
 
 
 
 
 
9
.
6
 
 
 
 
 
 
 
 
 
 
 
2
6
.
0
 
 
 

1
3
9
8
2
1
 
 
 
 
 
1
9
.
3
 
 
 
 
 
2
9
.
9
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
9
.
2
 
 
 
 
 
 
1
1
.
0
 
 
 
 
 
 
 
 
 
 
 
4
3
.
0
 
 
 

1
8
6
7
 
 
 
 
 
 
 
1
5
.
7
 
 
 
 
 
1
7
.
6
 
 
 
 
 
 
 
3
.
2
 
 
 
 
 
 
 
 
 
 
4
.
7
 
 
 
 
 
 
 
8
.
4
 
 
 
 
 
 
 
 
 
 
 
2
0
.
0
 
 
 


 
 
 
 
 
 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
.
.
.
 
 
N
N
W
 
 
N
W
 
 
S
 
 
\

2
2
9
2
6
 
 
 
 
 
 
 
 
 
 
 
3
1
.
0
 
 
 
 
 
 
 
 
 
 
2
8
.
0
 
 
 
 
 
 
 
 
 
7
4
.
0
 
 
 
 
 
 
 
 
 
7
3
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

8
0
7
3
5
 
 
 
 
 
 
 
 
 
 
 
1
3
.
0
 
 
 
 
 
 
 
 
 
 
2
4
.
0
 
 
 
 
 
 
 
 
 
7
4
.
0
 
 
 
 
 
 
 
 
 
5
5
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

1
2
1
7
6
4
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
1
1
.
0
 
 
 
 
 
 
 
 
 
8
5
.
0
 
 
 
 
 
 
 
 
 
4
7
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

1
3
9
8
2
1
 
 
 
 
 
 
 
 
 
 
2
6
.
0
 
 
 
 
 
 
 
 
 
 
1
7
.
0
 
 
 
 
 
 
 
 
 
4
4
.
0
 
 
 
 
 
 
 
 
 
3
7
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

1
8
6
7
 
 
 
 
 
 
 
 
 
 
 
 
1
1
.
0
 
 
 
 
 
 
 
 
 
 
1
3
.
0
 
 
 
 
 
 
 
 
1
0
0
.
0
 
 
 
 
 
 
 
 
1
0
0
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 


 
 
 
 
 
 
 
 
S
E
 
 
S
S
E
 
 
S
S
W
 
 
S
W
 
 
W
 
 
W
N
W
 
 
W
S
W
 
 

2
2
9
2
6
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

8
0
7
3
5
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

1
2
1
7
6
4
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
1
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

1
3
9
8
2
1
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

1
8
6
7
 
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 


[
5
 
r
o
w
s
 
x
 
1
1
8
 
c
o
l
u
m
n
s
]
</pre>
마
찬
가
지
로
,
 
`
X
_
t
e
s
t
`
 
테
스
트
 
세
트
를
 
생
성
하
겠
습
니
다
.



```python
X
_
t
e
s
t
 
=
 
p
d
.
c
o
n
c
a
t
(
[
X
_
t
e
s
t
[
n
u
m
e
r
i
c
a
l
]
,
 
X
_
t
e
s
t
[
[
'
R
a
i
n
T
o
d
a
y
_
0
'
,
 
'
R
a
i
n
T
o
d
a
y
_
1
'
]
]
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
e
s
t
.
L
o
c
a
t
i
o
n
)
,
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
e
s
t
.
W
i
n
d
G
u
s
t
D
i
r
)
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
e
s
t
.
W
i
n
d
D
i
r
9
a
m
)
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
d
.
g
e
t
_
d
u
m
m
i
e
s
(
X
_
t
e
s
t
.
W
i
n
d
D
i
r
3
p
m
)
]
,
 
a
x
i
s
=
1
)
```


```python
X
_
t
e
s
t
.
h
e
a
d
(
)
```

<pre>
 
 
 
 
 
 
 
 
M
i
n
T
e
m
p
 
 
M
a
x
T
e
m
p
 
 
R
a
i
n
f
a
l
l
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
\

1
3
8
1
7
5
 
 
 
 
 
2
1
.
9
 
 
 
 
 
3
9
.
4
 
 
 
 
 
 
 
1
.
6
 
 
 
 
 
 
 
 
 
1
1
.
2
 
 
 
 
 
 
1
1
.
5
 
 
 
 
 
 
 
 
 
 
 
5
7
.
0
 
 
 

3
8
6
3
8
 
 
 
 
 
 
2
0
.
5
 
 
 
 
 
3
7
.
5
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
9
.
2
 
 
 
 
 
 
 
8
.
4
 
 
 
 
 
 
 
 
 
 
 
5
9
.
0
 
 
 

1
2
4
0
5
8
 
 
 
 
 
 
5
.
1
 
 
 
 
 
1
7
.
2
 
 
 
 
 
 
 
0
.
2
 
 
 
 
 
 
 
 
 
 
4
.
7
 
 
 
 
 
 
 
8
.
4
 
 
 
 
 
 
 
 
 
 
 
5
0
.
0
 
 
 

9
9
2
1
4
 
 
 
 
 
 
1
1
.
9
 
 
 
 
 
1
6
.
8
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
 
4
.
7
 
 
 
 
 
 
 
8
.
4
 
 
 
 
 
 
 
 
 
 
 
2
8
.
0
 
 
 

2
5
0
9
7
 
 
 
 
 
 
 
7
.
5
 
 
 
 
 
2
1
.
3
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
4
.
7
 
 
 
 
 
 
 
8
.
4
 
 
 
 
 
 
 
 
 
 
 
1
5
.
0
 
 
 


 
 
 
 
 
 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
.
.
.
 
 
N
N
W
 
 
N
W
 
 
S
 
 
\

1
3
8
1
7
5
 
 
 
 
 
 
 
 
 
 
2
0
.
0
 
 
 
 
 
 
 
 
 
 
3
3
.
0
 
 
 
 
 
 
 
 
 
5
0
.
0
 
 
 
 
 
 
 
 
 
2
6
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

3
8
6
3
8
 
 
 
 
 
 
 
 
 
 
 
1
7
.
0
 
 
 
 
 
 
 
 
 
 
2
0
.
0
 
 
 
 
 
 
 
 
 
4
7
.
0
 
 
 
 
 
 
 
 
 
2
2
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

1
2
4
0
5
8
 
 
 
 
 
 
 
 
 
 
2
8
.
0
 
 
 
 
 
 
 
 
 
 
2
2
.
0
 
 
 
 
 
 
 
 
 
6
8
.
0
 
 
 
 
 
 
 
 
 
5
1
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

9
9
2
1
4
 
 
 
 
 
 
 
 
 
 
 
1
1
.
0
 
 
 
 
 
 
 
 
 
 
1
3
.
0
 
 
 
 
 
 
 
 
 
8
0
.
0
 
 
 
 
 
 
 
 
 
7
9
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 

2
5
0
9
7
 
 
 
 
 
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
 
 
7
.
0
 
 
 
 
 
 
 
 
 
8
8
.
0
 
 
 
 
 
 
 
 
 
5
2
.
0
 
 
.
.
.
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 


 
 
 
 
 
 
 
 
S
E
 
 
S
S
E
 
 
S
S
W
 
 
S
W
 
 
W
 
 
W
N
W
 
 
W
S
W
 
 

1
3
8
1
7
5
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

3
8
6
3
8
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

1
2
4
0
5
8
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
1
 
 
 
 
0
 
 
 
 
0
 
 

9
9
2
1
4
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
1
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 

2
5
0
9
7
 
 
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 
 
0
 
 
0
 
 
 
 
0
 
 
 
 
0
 
 


[
5
 
r
o
w
s
 
x
 
1
1
8
 
c
o
l
u
m
n
s
]
</pre>
이
제
 
모
델
 
구
축
을
 
위
해
 
훈
련
 
및
 
테
스
트
 
세
트
가
 
준
비
되
었
습
니
다
.
 
그
 
전
에
,
 
모
든
 
f
e
a
t
u
r
e
 
변
수
를
 
동
일
한
 
척
도
로
 
매
핑
해
야
 
합
니
다
.
 
이
를
 
`
f
e
a
t
u
r
e
 
s
c
a
l
i
n
g
`
이
라
고
 
합
니
다
.
 
다
음
과
 
같
이
 
수
행
하
겠
습
니
다
.


#
 
*
*
1
1
.
 
F
e
a
t
u
r
e
 
S
c
a
l
i
n
g
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
1
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
X
_
t
r
a
i
n
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
M
a
x
T
e
m
p
 
 
 
 
 
 
 
R
a
i
n
f
a
l
l
 
 
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
1
2
.
1
9
0
1
8
9
 
 
 
 
 
 
2
3
.
2
0
3
1
0
7
 
 
 
 
 
 
 
0
.
6
7
0
8
0
0
 
 
 
 
 
 
 
5
.
0
9
3
3
6
2
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
6
.
3
6
6
8
9
3
 
 
 
 
 
 
 
7
.
0
8
5
4
0
8
 
 
 
 
 
 
 
1
.
1
8
1
5
1
2
 
 
 
 
 
 
 
2
.
8
0
0
2
0
0
 
 
 

m
i
n
 
 
 
 
 
 
 
 
-
8
.
5
0
0
0
0
0
 
 
 
 
 
 
-
4
.
8
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
7
.
7
0
0
0
0
0
 
 
 
 
 
 
1
8
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
4
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
1
2
.
0
0
0
0
0
0
 
 
 
 
 
 
2
2
.
6
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
4
.
7
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
1
6
.
8
0
0
0
0
0
 
 
 
 
 
 
2
8
.
2
0
0
0
0
0
 
 
 
 
 
 
 
0
.
6
0
0
0
0
0
 
 
 
 
 
 
 
5
.
2
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
3
1
.
9
0
0
0
0
0
 
 
 
 
 
 
4
8
.
1
0
0
0
0
0
 
 
 
 
 
 
 
3
.
2
0
0
0
0
0
 
 
 
 
 
 
2
1
.
8
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
7
.
9
8
2
4
7
6
 
 
 
 
 
 
3
9
.
9
8
2
0
9
1
 
 
 
 
 
 
1
4
.
0
2
9
3
8
1
 
 
 
 
 
 
1
8
.
6
8
7
4
6
6
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
7
6
1
6
3
9
 
 
 
 
 
 
1
3
.
1
2
7
9
5
3
 
 
 
 
 
 
 
8
.
8
3
5
5
9
6
 
 
 
 
 
 
 
8
.
7
0
0
6
1
8
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
6
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
8
.
2
0
0
0
0
0
 
 
 
 
 
 
3
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
7
.
0
0
0
0
0
0
 
 
 
 
 
 
1
3
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
8
.
4
0
0
0
0
0
 
 
 
 
 
 
3
9
.
0
0
0
0
0
0
 
 
 
 
 
 
1
3
.
0
0
0
0
0
0
 
 
 
 
 
 
1
9
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
8
.
6
0
0
0
0
0
 
 
 
 
 
 
4
6
.
0
0
0
0
0
0
 
 
 
 
 
 
1
9
.
0
0
0
0
0
0
 
 
 
 
 
 
2
4
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
1
4
.
5
0
0
0
0
0
 
 
 
 
 
1
3
5
.
0
0
0
0
0
0
 
 
 
 
 
 
5
5
.
0
0
0
0
0
0
 
 
 
 
 
 
5
7
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
N
N
W
 
 
 
 
 
 
 
 
 
 
 
 
 
N
W
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
.
.
.
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
6
8
.
9
5
0
6
9
1
 
 
 
 
 
 
5
1
.
6
0
5
8
2
8
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
5
4
0
7
8
 
 
 
 
 
 
 
0
.
0
5
9
1
2
3
 
 
 

s
t
d
 
 
 
 
 
 
 
 
1
8
.
8
1
1
4
3
7
 
 
 
 
 
 
2
0
.
4
3
9
9
9
9
 
 
.
.
.
 
 
 
 
 
 
 
0
.
2
2
6
1
7
3
 
 
 
 
 
 
 
0
.
2
3
5
8
5
5
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
5
7
.
0
0
0
0
0
0
 
 
 
 
 
 
3
7
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
7
0
.
0
0
0
0
0
0
 
 
 
 
 
 
5
2
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
8
3
.
0
0
0
0
0
0
 
 
 
 
 
 
6
5
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
1
0
0
.
0
0
0
0
0
0
 
 
 
 
 
1
0
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
 
 
 
 
 
 
 
 
 
 
 
 
 
S
E
 
 
 
 
 
 
 
 
 
 
 
 
S
S
E
 
 
 
 
 
 
 
 
 
 
 
 
S
S
W
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
6
8
4
4
7
 
 
 
 
 
 
 
0
.
1
0
3
7
2
3
 
 
 
 
 
 
 
0
.
0
6
5
2
2
4
 
 
 
 
 
 
 
0
.
0
5
6
0
5
5
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
2
5
2
5
1
2
 
 
 
 
 
 
 
0
.
3
0
4
9
0
2
 
 
 
 
 
 
 
0
.
2
4
6
9
2
2
 
 
 
 
 
 
 
0
.
2
3
0
0
2
9
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
W
 
 
 
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
 
 
 
 
W
N
W
 
 
 
 
 
 
 
 
 
 
 
 
W
S
W
 
 

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
6
4
7
8
6
 
 
 
 
 
 
 
0
.
0
6
9
3
2
3
 
 
 
 
 
 
 
0
.
0
6
0
3
0
9
 
 
 
 
 
 
 
0
.
0
6
4
9
5
8
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
2
4
6
1
4
9
 
 
 
 
 
 
 
0
.
2
5
4
0
0
4
 
 
 
 
 
 
 
0
.
2
3
8
0
5
9
 
 
 
 
 
 
 
0
.
2
4
6
4
5
2
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 


[
8
 
r
o
w
s
 
x
 
1
1
8
 
c
o
l
u
m
n
s
]
</pre>

```python
c
o
l
s
 
=
 
X
_
t
r
a
i
n
.
c
o
l
u
m
n
s
```


```python
f
r
o
m
 
s
k
l
e
a
r
n
.
p
r
e
p
r
o
c
e
s
s
i
n
g
 
i
m
p
o
r
t
 
M
i
n
M
a
x
S
c
a
l
e
r


s
c
a
l
e
r
 
=
 
M
i
n
M
a
x
S
c
a
l
e
r
(
)


X
_
t
r
a
i
n
 
=
 
s
c
a
l
e
r
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
X
_
t
r
a
i
n
)


X
_
t
e
s
t
 
=
 
s
c
a
l
e
r
.
t
r
a
n
s
f
o
r
m
(
X
_
t
e
s
t
)

```


```python
X
_
t
r
a
i
n
 
=
 
p
d
.
D
a
t
a
F
r
a
m
e
(
X
_
t
r
a
i
n
,
 
c
o
l
u
m
n
s
=
[
c
o
l
s
]
)
```


```python
X
_
t
e
s
t
 
=
 
p
d
.
D
a
t
a
F
r
a
m
e
(
X
_
t
e
s
t
,
 
c
o
l
u
m
n
s
=
[
c
o
l
s
]
)
```


```python
X
_
t
r
a
i
n
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
M
i
n
T
e
m
p
 
 
 
 
 
 
 
 
M
a
x
T
e
m
p
 
 
 
 
 
 
 
R
a
i
n
f
a
l
l
 
 
 
 
E
v
a
p
o
r
a
t
i
o
n
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
5
1
2
1
3
3
 
 
 
 
 
 
 
0
.
5
2
9
3
5
9
 
 
 
 
 
 
 
0
.
2
0
9
6
2
5
 
 
 
 
 
 
 
0
.
2
3
3
6
4
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
1
5
7
5
9
6
 
 
 
 
 
 
 
0
.
1
3
3
9
4
0
 
 
 
 
 
 
 
0
.
3
6
9
2
2
3
 
 
 
 
 
 
 
0
.
1
2
8
4
5
0
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
4
0
0
9
9
0
 
 
 
 
 
 
 
0
.
4
3
1
0
0
2
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
1
8
3
4
8
6
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
5
0
7
4
2
6
 
 
 
 
 
 
 
0
.
5
1
7
9
5
8
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
2
1
5
5
9
6
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
6
2
6
2
3
8
 
 
 
 
 
 
 
0
.
6
2
3
8
1
9
 
 
 
 
 
 
 
0
.
1
8
7
5
0
0
 
 
 
 
 
 
 
0
.
2
3
8
5
3
2
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
S
u
n
s
h
i
n
e
 
 
W
i
n
d
G
u
s
t
S
p
e
e
d
 
 
 
W
i
n
d
S
p
e
e
d
9
a
m
 
 
 
W
i
n
d
S
p
e
e
d
3
p
m
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
5
5
0
5
1
6
 
 
 
 
 
 
 
0
.
2
6
3
4
2
7
 
 
 
 
 
 
 
0
.
2
5
5
0
8
0
 
 
 
 
 
 
 
0
.
3
2
7
8
5
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
1
9
0
4
5
8
 
 
 
 
 
 
 
0
.
1
0
1
7
6
7
 
 
 
 
 
 
 
0
.
1
6
0
6
4
7
 
 
 
 
 
 
 
0
.
1
5
2
6
4
2
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
5
6
5
5
1
7
 
 
 
 
 
 
 
0
.
1
9
3
7
9
8
 
 
 
 
 
 
 
0
.
1
2
7
2
7
3
 
 
 
 
 
 
 
0
.
2
2
8
0
7
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
5
7
9
3
1
0
 
 
 
 
 
 
 
0
.
2
5
5
8
1
4
 
 
 
 
 
 
 
0
.
2
3
6
3
6
4
 
 
 
 
 
 
 
0
.
3
3
3
3
3
3
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
5
9
3
1
0
3
 
 
 
 
 
 
 
0
.
3
1
0
0
7
8
 
 
 
 
 
 
 
0
.
3
4
5
4
5
5
 
 
 
 
 
 
 
0
.
4
2
1
0
5
3
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
H
u
m
i
d
i
t
y
9
a
m
 
 
 
 
H
u
m
i
d
i
t
y
3
p
m
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
N
N
W
 
 
 
 
 
 
 
 
 
 
 
 
 
N
W
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
.
.
.
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
6
8
9
5
0
7
 
 
 
 
 
 
 
0
.
5
1
6
0
5
8
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
5
4
0
7
8
 
 
 
 
 
 
 
0
.
0
5
9
1
2
3
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
1
8
8
1
1
4
 
 
 
 
 
 
 
0
.
2
0
4
4
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
2
2
6
1
7
3
 
 
 
 
 
 
 
0
.
2
3
5
8
5
5
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
5
7
0
0
0
0
 
 
 
 
 
 
 
0
.
3
7
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
7
0
0
0
0
0
 
 
 
 
 
 
 
0
.
5
2
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
8
3
0
0
0
0
 
 
 
 
 
 
 
0
.
6
5
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
 
 
 
 
 
 
 
 
 
 
 
 
 
S
E
 
 
 
 
 
 
 
 
 
 
 
 
S
S
E
 
 
 
 
 
 
 
 
 
 
 
 
S
S
W
 
 
\

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
6
8
4
4
7
 
 
 
 
 
 
 
0
.
1
0
3
7
2
3
 
 
 
 
 
 
 
0
.
0
6
5
2
2
4
 
 
 
 
 
 
 
0
.
0
5
6
0
5
5
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
2
5
2
5
1
2
 
 
 
 
 
 
 
0
.
3
0
4
9
0
2
 
 
 
 
 
 
 
0
.
2
4
6
9
2
2
 
 
 
 
 
 
 
0
.
2
3
0
0
2
9
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
W
 
 
 
 
 
 
 
 
 
 
 
 
 
 
W
 
 
 
 
 
 
 
 
 
 
 
 
W
N
W
 
 
 
 
 
 
 
 
 
 
 
 
W
S
W
 
 

c
o
u
n
t
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 
1
1
6
3
6
8
.
0
0
0
0
0
0
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
6
4
7
8
6
 
 
 
 
 
 
 
0
.
0
6
9
3
2
3
 
 
 
 
 
 
 
0
.
0
6
0
3
0
9
 
 
 
 
 
 
 
0
.
0
6
4
9
5
8
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
2
4
6
1
4
9
 
 
 
 
 
 
 
0
.
2
5
4
0
0
4
 
 
 
 
 
 
 
0
.
2
3
8
0
5
9
 
 
 
 
 
 
 
0
.
2
4
6
4
5
2
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 


[
8
 
r
o
w
s
 
x
 
1
1
8
 
c
o
l
u
m
n
s
]
</pre>
이
제
 
우
리
는
 
로
지
스
틱
 
회
귀
 
분
류
기
에
 
입
력
할
 
준
비
가
 
된
 
'
X
_
t
r
a
i
n
'
 
데
이
터
셋
이
 
있
습
니
다
.
 
저
는
 
다
음
과
 
같
이
 
수
행
하
겠
습
니
다
.


#
 
*
*
1
2
.
 
모
델
 
학
습
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
2
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)


`
y
_
t
r
a
i
n
,
 
y
_
t
e
s
t
`
의
 
결
측
치
를
 
처
리
해
준
다
.



```python
f
r
o
m
 
s
k
l
e
a
r
n
.
p
r
e
p
r
o
c
e
s
s
i
n
g
 
i
m
p
o
r
t
 
L
a
b
e
l
E
n
c
o
d
e
r


y
_
t
r
a
i
n
 
=
 
p
d
.
D
a
t
a
F
r
a
m
e
(
y
_
t
r
a
i
n
)

y
_
t
e
s
t
 
=
 
p
d
.
D
a
t
a
F
r
a
m
e
(
y
_
t
e
s
t
)


y
_
t
r
a
i
n
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
f
i
l
l
n
a
(
y
_
t
r
a
i
n
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
m
o
d
e
(
)
[
0
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)

y
_
t
e
s
t
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
f
i
l
l
n
a
(
y
_
t
e
s
t
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
m
o
d
e
(
)
[
0
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)


t
r
a
i
n
_
l
e
 
=
 
L
a
b
e
l
E
n
c
o
d
e
r
(
)

t
e
s
t
_
l
e
 
=
 
L
a
b
e
l
E
n
c
o
d
e
r
(
)


t
r
a
i
n
_
l
e
.
f
i
t
(
y
_
t
r
a
i
n
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
a
s
t
y
p
e
(
'
s
t
r
'
)
.
d
r
o
p
_
d
u
p
l
i
c
a
t
e
s
(
)
)

t
e
s
t
_
l
e
.
f
i
t
(
y
_
t
e
s
t
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
a
s
t
y
p
e
(
'
s
t
r
'
)
.
d
r
o
p
_
d
u
p
l
i
c
a
t
e
s
(
)
)


y
_
t
r
a
i
n
[
'
e
n
c
'
]
 
=
 
t
r
a
i
n
_
l
e
.
t
r
a
n
s
f
o
r
m
(
y
_
t
r
a
i
n
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
a
s
t
y
p
e
(
'
s
t
r
'
)
)

y
_
t
e
s
t
[
'
e
n
c
'
]
 
=
 
t
r
a
i
n
_
l
e
.
t
r
a
n
s
f
o
r
m
(
y
_
t
e
s
t
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
.
a
s
t
y
p
e
(
'
s
t
r
'
)
)


y
_
t
r
a
i
n
.
d
r
o
p
(
c
o
l
u
m
n
s
=
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)

y
_
t
e
s
t
.
d
r
o
p
(
c
o
l
u
m
n
s
=
[
'
R
a
i
n
T
o
m
o
r
r
o
w
'
]
,
 
i
n
p
l
a
c
e
=
T
r
u
e
)
```

학
습
시
킨
다
.



```python
#
 
t
r
a
i
n
 
a
 
l
o
g
i
s
t
i
c
 
r
e
g
r
e
s
s
i
o
n
 
m
o
d
e
l
 
o
n
 
t
h
e
 
t
r
a
i
n
i
n
g
 
s
e
t

f
r
o
m
 
s
k
l
e
a
r
n
.
l
i
n
e
a
r
_
m
o
d
e
l
 
i
m
p
o
r
t
 
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n



#
 
i
n
s
t
a
n
t
i
a
t
e
 
t
h
e
 
m
o
d
e
l

l
o
g
r
e
g
 
=
 
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
)



#
 
f
i
t
 
t
h
e
 
m
o
d
e
l

l
o
g
r
e
g
.
f
i
t
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)

```

<pre>
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
1
.
0
,
 
c
l
a
s
s
_
w
e
i
g
h
t
=
N
o
n
e
,
 
d
u
a
l
=
F
a
l
s
e
,
 
f
i
t
_
i
n
t
e
r
c
e
p
t
=
T
r
u
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
e
r
c
e
p
t
_
s
c
a
l
i
n
g
=
1
,
 
l
1
_
r
a
t
i
o
=
N
o
n
e
,
 
m
a
x
_
i
t
e
r
=
1
0
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
u
l
t
i
_
c
l
a
s
s
=
'
w
a
r
n
'
,
 
n
_
j
o
b
s
=
N
o
n
e
,
 
p
e
n
a
l
t
y
=
'
l
2
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
t
o
l
=
0
.
0
0
0
1
,
 
v
e
r
b
o
s
e
=
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
w
a
r
m
_
s
t
a
r
t
=
F
a
l
s
e
)
</pre>
#
 
*
*
1
3
.
 
예
측
결
과
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
3
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
y
_
p
r
e
d
_
t
e
s
t
 
=
 
l
o
g
r
e
g
.
p
r
e
d
i
c
t
(
X
_
t
e
s
t
)


y
_
p
r
e
d
_
t
e
s
t
```

<pre>
a
r
r
a
y
(
[
0
,
 
0
,
 
0
,
 
.
.
.
,
 
1
,
 
0
,
 
0
]
)
</pre>
#
#
#
 
p
r
e
d
i
c
t
_
p
r
o
b
a
 
메
서
드
는
 
이
 
경
우
에
 
대
상
 
변
수
(
0
과
 
1
)
의
 
확
률
을
 
배
열
 
형
태
로
 
제
공
합
니
다
.




여
기
서
 
`
0
은
 
비
가
 
오
지
 
않
을
 
확
률
`
이
고
,
 
`
1
은
 
비
가
 
올
 
확
률
`
입
니
다
.



```python
#
 
p
r
o
b
a
b
i
l
i
t
y
 
o
f
 
g
e
t
t
i
n
g
 
o
u
t
p
u
t
 
a
s
 
0
 
-
 
n
o
 
r
a
i
n


l
o
g
r
e
g
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
X
_
t
e
s
t
)
[
:
,
0
]
```

<pre>
a
r
r
a
y
(
[
0
.
8
3
2
1
8
0
1
2
,
 
0
.
7
4
5
4
7
8
9
7
,
 
0
.
7
9
8
6
4
8
9
9
,
 
.
.
.
,
 
0
.
4
2
0
2
5
8
2
8
,
 
0
.
6
5
7
4
6
9
9
1
,

 
 
 
 
 
 
 
0
.
9
6
9
5
4
6
5
3
]
)
</pre>

```python
#
 
p
r
o
b
a
b
i
l
i
t
y
 
o
f
 
g
e
t
t
i
n
g
 
o
u
t
p
u
t
 
a
s
 
1
 
-
 
r
a
i
n


l
o
g
r
e
g
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
X
_
t
e
s
t
)
[
:
,
1
]
```

<pre>
a
r
r
a
y
(
[
0
.
1
6
7
8
1
9
8
8
,
 
0
.
2
5
4
5
2
1
0
3
,
 
0
.
2
0
1
3
5
1
0
1
,
 
.
.
.
,
 
0
.
5
7
9
7
4
1
7
2
,
 
0
.
3
4
2
5
3
0
0
9
,

 
 
 
 
 
 
 
0
.
0
3
0
4
5
3
4
7
]
)
</pre>
#
 
*
*
1
4
.
 
정
확
도
 
점
수
 
확
인
하
기
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
4
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
f
r
o
m
 
s
k
l
e
a
r
n
.
m
e
t
r
i
c
s
 
i
m
p
o
r
t
 
a
c
c
u
r
a
c
y
_
s
c
o
r
e


p
r
i
n
t
(
'
M
o
d
e
l
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
{
0
:
0
.
4
f
}
'
.
 
f
o
r
m
a
t
(
a
c
c
u
r
a
c
y
_
s
c
o
r
e
(
y
_
t
e
s
t
,
 
y
_
p
r
e
d
_
t
e
s
t
)
)
)
```

<pre>
M
o
d
e
l
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
8
4
8
4

</pre>
여
기
서
 
y
_
t
e
s
t
는
 
테
스
트
 
세
트
에
서
의
 
실
제
 
클
래
스
 
레
이
블
이
고
,
 
y
_
p
r
e
d
_
t
e
s
t
는
 
예
측
된
 
클
래
스
 
레
이
블
입
니
다
.


#
#
#
 
학
습
세
트
와
 
테
스
트
 
세
트
비
교


이
제
,
 
과
적
합
(
o
v
e
r
f
i
t
t
i
n
g
)
을
 
확
인
하
기
 
위
해
 
학
습
 
세
트
(
t
r
a
i
n
-
s
e
t
)
와
 
테
스
트
 
세
트
(
t
e
s
t
-
s
e
t
)
 
정
확
도
를
 
비
교
해
보
겠
습
니
다
.



```python
y
_
p
r
e
d
_
t
r
a
i
n
 
=
 
l
o
g
r
e
g
.
p
r
e
d
i
c
t
(
X
_
t
r
a
i
n
)


y
_
p
r
e
d
_
t
r
a
i
n
```

<pre>
a
r
r
a
y
(
[
0
,
 
0
,
 
0
,
 
.
.
.
,
 
0
,
 
0
,
 
0
]
)
</pre>

```python
p
r
i
n
t
(
'
T
r
a
i
n
i
n
g
-
s
e
t
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
{
0
:
0
.
4
f
}
'
.
 
f
o
r
m
a
t
(
a
c
c
u
r
a
c
y
_
s
c
o
r
e
(
y
_
t
r
a
i
n
,
 
y
_
p
r
e
d
_
t
r
a
i
n
)
)
)
```

<pre>
T
r
a
i
n
i
n
g
-
s
e
t
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
8
4
8
8

</pre>
#
#
#
 
C
h
e
c
k
 
f
o
r
 
o
v
e
r
f
i
t
t
i
n
g
 
a
n
d
 
u
n
d
e
r
f
i
t
t
i
n
g



```python
#
 
p
r
i
n
t
 
t
h
e
 
s
c
o
r
e
s
 
o
n
 
t
r
a
i
n
i
n
g
 
a
n
d
 
t
e
s
t
 
s
e
t


p
r
i
n
t
(
'
T
r
a
i
n
i
n
g
 
s
e
t
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
l
o
g
r
e
g
.
s
c
o
r
e
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)
)
)


p
r
i
n
t
(
'
T
e
s
t
 
s
e
t
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
l
o
g
r
e
g
.
s
c
o
r
e
(
X
_
t
e
s
t
,
 
y
_
t
e
s
t
)
)
)
```

<pre>
T
r
a
i
n
i
n
g
 
s
e
t
 
s
c
o
r
e
:
 
0
.
8
4
8
8

T
e
s
t
 
s
e
t
 
s
c
o
r
e
:
 
0
.
8
4
8
4

</pre>
두
 
점
수
차
이
가
 
거
의
 
나
지
 
않
고
 
비
슷
한
 
것
을
 
보
아
 
과
적
합
문
제
는
 
없
다
.




로
지
스
틱
 
회
귀
에
서
는
 
C
의
 
기
본
값
인
 
1
을
 
사
용
합
니
다
.
 
이
 
값
은
 
학
습
 
세
트
와
 
테
스
트
 
세
트
 
모
두
 
약
 
8
5
%
의
 
정
확
도
로
 
좋
은
 
성
능
을
 
제
공
합
니
다
.
 
그
러
나
 
학
습
 
세
트
와
 
테
스
트
 
세
트
 
모
두
 
모
델
 
성
능
이
 
매
우
 
비
슷
하
기
 
때
문
에
 
과
소
적
합
(
u
n
d
e
r
f
i
t
t
i
n
g
)
의
 
가
능
성
이
 
있
습
니
다
.




따
라
서
,
 
C
를
 
증
가
시
켜
 
더
 
유
연
한
 
모
델
을
 
만
들
어
보
겠
습
니
다
.



```python
#
 
f
i
t
 
t
h
e
 
L
o
g
s
i
t
i
c
 
R
e
g
r
e
s
s
i
o
n
 
m
o
d
e
l
 
w
i
t
h
 
C
=
1
0
0


#
 
i
n
s
t
a
n
t
i
a
t
e
 
t
h
e
 
m
o
d
e
l

l
o
g
r
e
g
1
0
0
 
=
 
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
1
0
0
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
)



#
 
f
i
t
 
t
h
e
 
m
o
d
e
l

l
o
g
r
e
g
1
0
0
.
f
i
t
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)
```

<pre>
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
1
0
0
,
 
c
l
a
s
s
_
w
e
i
g
h
t
=
N
o
n
e
,
 
d
u
a
l
=
F
a
l
s
e
,
 
f
i
t
_
i
n
t
e
r
c
e
p
t
=
T
r
u
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
e
r
c
e
p
t
_
s
c
a
l
i
n
g
=
1
,
 
l
1
_
r
a
t
i
o
=
N
o
n
e
,
 
m
a
x
_
i
t
e
r
=
1
0
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
u
l
t
i
_
c
l
a
s
s
=
'
w
a
r
n
'
,
 
n
_
j
o
b
s
=
N
o
n
e
,
 
p
e
n
a
l
t
y
=
'
l
2
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
t
o
l
=
0
.
0
0
0
1
,
 
v
e
r
b
o
s
e
=
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
w
a
r
m
_
s
t
a
r
t
=
F
a
l
s
e
)
</pre>

```python
#
 
p
r
i
n
t
 
t
h
e
 
s
c
o
r
e
s
 
o
n
 
t
r
a
i
n
i
n
g
 
a
n
d
 
t
e
s
t
 
s
e
t


p
r
i
n
t
(
'
T
r
a
i
n
i
n
g
 
s
e
t
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
l
o
g
r
e
g
1
0
0
.
s
c
o
r
e
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)
)
)


p
r
i
n
t
(
'
T
e
s
t
 
s
e
t
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
l
o
g
r
e
g
1
0
0
.
s
c
o
r
e
(
X
_
t
e
s
t
,
 
y
_
t
e
s
t
)
)
)
```

<pre>
T
r
a
i
n
i
n
g
 
s
e
t
 
s
c
o
r
e
:
 
0
.
8
4
8
9

T
e
s
t
 
s
e
t
 
s
c
o
r
e
:
 
0
.
8
4
9
1

</pre>
위
의
 
결
과
에
서
 
볼
 
수
 
있
듯
이
,
 
C
=
1
0
0
인
 
경
우
 
테
스
트
 
세
트
의
 
정
확
도
가
 
더
 
높
게
 
나
타
났
으
며
,
 
약
간
의
 
증
가
한
 
학
습
 
세
트
 
정
확
도
도
 
확
인
할
 
수
 
있
습
니
다
.
 
따
라
서
,
 
더
 
복
잡
한
 
모
델
이
 
더
 
나
은
 
성
능
을
 
발
휘
할
 
것
으
로
 
결
론
을
 
내
릴
 
수
 
있
습
니
다
.


이
제
,
 
C
의
 
기
본
값
인
 
1
보
다
 
더
 
규
제
화
(
r
e
g
u
l
a
r
i
z
e
d
)
된
 
모
델
을
 
사
용
할
 
때
 
어
떤
 
일
이
 
일
어
나
는
지
 
알
아
보
기
 
위
해
 
C
=
0
.
0
1
로
 
설
정
해
보
겠
습
니
다
.



```python
#
 
f
i
t
 
t
h
e
 
L
o
g
s
i
t
i
c
 
R
e
g
r
e
s
s
i
o
n
 
m
o
d
e
l
 
w
i
t
h
 
C
=
0
0
1


#
 
i
n
s
t
a
n
t
i
a
t
e
 
t
h
e
 
m
o
d
e
l

l
o
g
r
e
g
0
0
1
 
=
 
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
0
.
0
1
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
)



#
 
f
i
t
 
t
h
e
 
m
o
d
e
l

l
o
g
r
e
g
0
0
1
.
f
i
t
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)
```

<pre>
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
0
.
0
1
,
 
c
l
a
s
s
_
w
e
i
g
h
t
=
N
o
n
e
,
 
d
u
a
l
=
F
a
l
s
e
,
 
f
i
t
_
i
n
t
e
r
c
e
p
t
=
T
r
u
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
e
r
c
e
p
t
_
s
c
a
l
i
n
g
=
1
,
 
l
1
_
r
a
t
i
o
=
N
o
n
e
,
 
m
a
x
_
i
t
e
r
=
1
0
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
u
l
t
i
_
c
l
a
s
s
=
'
w
a
r
n
'
,
 
n
_
j
o
b
s
=
N
o
n
e
,
 
p
e
n
a
l
t
y
=
'
l
2
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
t
o
l
=
0
.
0
0
0
1
,
 
v
e
r
b
o
s
e
=
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
w
a
r
m
_
s
t
a
r
t
=
F
a
l
s
e
)
</pre>

```python
#
 
p
r
i
n
t
 
t
h
e
 
s
c
o
r
e
s
 
o
n
 
t
r
a
i
n
i
n
g
 
a
n
d
 
t
e
s
t
 
s
e
t


p
r
i
n
t
(
'
T
r
a
i
n
i
n
g
 
s
e
t
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
l
o
g
r
e
g
0
0
1
.
s
c
o
r
e
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)
)
)


p
r
i
n
t
(
'
T
e
s
t
 
s
e
t
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
l
o
g
r
e
g
0
0
1
.
s
c
o
r
e
(
X
_
t
e
s
t
,
 
y
_
t
e
s
t
)
)
)
```

<pre>
T
r
a
i
n
i
n
g
 
s
e
t
 
s
c
o
r
e
:
 
0
.
8
4
2
7

T
e
s
t
 
s
e
t
 
s
c
o
r
e
:
 
0
.
8
4
1
8

</pre>
따
라
서
,
 
C
=
0
.
0
1
로
 
더
 
규
제
화
된
 
모
델
을
 
사
용
하
면
 
기
본
 
매
개
변
수
에
 
비
해
 
학
습
 
세
트
와
 
테
스
트
 
세
트
의
 
정
확
도
가
 
모
두
 
감
소
합
니
다
.


#
#
#
 
모
델
 
정
확
도
와
 
기
준
정
확
도
(
n
u
l
l
 
a
c
c
u
r
a
c
y
)
 
비
교
하
기




따
라
서
,
 
모
델
 
정
확
도
는
 
0
.
8
4
8
4
입
니
다
.
 
그
러
나
 
위
의
 
정
확
도
에
 
기
반
하
여
 
우
리
 
모
델
이
 
매
우
 
좋
다
고
 
말
할
 
수
는
 
없
습
니
다
.
 
기
준
 
정
확
도
(
n
u
l
l
 
a
c
c
u
r
a
c
y
)
와
 
비
교
해
야
 
합
니
다
.
 
기
준
 
정
확
도
는
 
가
장
 
빈
번
하
게
 
나
타
나
는
 
클
래
스
를
 
항
상
 
예
측
하
는
 
것
으
로
 
얻
을
 
수
 
있
는
 
정
확
도
입
니
다
.




따
라
서
,
 
먼
저
 
테
스
트
 
세
트
에
서
의
 
클
래
스
 
분
포
를
 
확
인
해
야
 
합
니
다
.



```python
#
 
c
h
e
c
k
 
c
l
a
s
s
 
d
i
s
t
r
i
b
u
t
i
o
n
 
i
n
 
t
e
s
t
 
s
e
t


y
_
t
e
s
t
_
s
e
r
i
e
s
 
=
 
y
_
t
e
s
t
.
i
l
o
c
[
:
,
 
0
]

y
_
t
e
s
t
_
s
e
r
i
e
s
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
0
 
 
 
 
2
2
7
2
6

1
 
 
 
 
 
6
3
6
6

N
a
m
e
:
 
e
n
c
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>
우
리
는
 
가
장
 
빈
번
한
 
클
래
스
의
 
발
생
 
빈
도
가
 
2
2
7
2
6
임
을
 
알
 
수
 
있
습
니
다
.
 
따
라
서
,
 
우
리
는
 
2
2
7
2
6
을
 
전
체
 
발
생
 
횟
수
로
 
나
누
어
 
n
u
l
l
 
정
확
도
(
n
u
l
l
 
a
c
c
u
r
a
c
y
)
를
 
계
산
할
 
수
 
있
습
니
다



```python
#
 
c
h
e
c
k
 
n
u
l
l
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e


n
u
l
l
_
a
c
c
u
r
a
c
y
 
=
 
(
2
2
7
2
6
/
(
2
2
7
2
6
+
6
3
6
6
)
)


p
r
i
n
t
(
'
N
u
l
l
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
{
0
:
0
.
4
f
}
'
.
 
f
o
r
m
a
t
(
n
u
l
l
_
a
c
c
u
r
a
c
y
)
)
```

<pre>
N
u
l
l
 
a
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
7
8
1
2

</pre>
번
역
:


우
리
는
 
모
델
 
정
확
도
 
점
수
가
 
0
.
8
4
8
4
이
지
만
 
널
(
n
u
l
l
)
 
정
확
도
 
점
수
가
 
0
.
7
8
1
2
임
을
 
알
 
수
 
있
습
니
다
.
 
따
라
서
,
 
우
리
는
 
로
지
스
틱
 
회
귀
 
모
델
이
 
클
래
스
 
레
이
블
을
 
예
측
하
는
 
데
 
아
주
 
좋
은
 
성
능
을
 
발
휘
하
고
 
있
다
고
 
결
론
지
을
 
수
 
있
습
니
다
.


이
제
 
위
의
 
분
석
을
 
바
탕
으
로
 
분
류
 
모
델
의
 
정
확
도
가
 
매
우
 
높
다
는
 
결
론
을
 
내
릴
 
수
 
있
습
니
다
.
 
우
리
 
모
델
은
 
클
래
스
 
레
이
블
을
 
예
측
하
는
 
데
 
매
우
 
잘
 
수
행
하
고
 
있
습
니
다
.




하
지
만
,
 
이
는
 
값
의
 
분
포
에
 
대
한
 
정
보
를
 
제
공
하
지
 
않
으
며
,
 
분
류
기
가
 
만
드
는
 
오
류
 
유
형
에
 
대
해
서
도
 
알
려
주
지
 
않
습
니
다
.




이
 
경
우
 
`
혼
동
 
행
렬
(
C
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
)
`
이
라
는
 
도
구
가
 
우
리
를
 
돕
게
 
됩
니
다
.


#
 
*
*
1
5
.
 
혼
동
 
행
렬
C
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
5
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)






혼
동
 
행
렬
(
C
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
)
은
 
분
류
 
알
고
리
즘
의
 
성
능
을
 
요
약
하
는
 
도
구
입
니
다
.
 
혼
동
 
행
렬
은
 
분
류
 
모
델
의
 
성
능
과
 
모
델
이
 
만
드
는
 
오
류
 
유
형
에
 
대
한
 
명
확
한
 
그
림
을
 
제
공
합
니
다
.
 
이
는
 
각
 
카
테
고
리
별
로
 
올
바
른
 
예
측
과
 
부
정
확
한
 
예
측
을
 
요
약
하
여
 
표
시
됩
니
다
.




분
류
 
모
델
 
성
능
을
 
평
가
할
 
때
는
 
다
음
 
4
가
지
 
결
과
가
 
가
능
합
니
다
.




참
 
긍
정
(
T
r
u
e
 
P
o
s
i
t
i
v
e
s
,
 
T
P
)
 
:
 
어
떤
 
관
측
치
가
 
특
정
 
클
래
스
에
 
속
한
다
고
 
예
측
하
고
 
실
제
로
 
그
 
클
래
스
에
 
속
할
 
때
 
참
 
긍
정
이
라
고
 
합
니
다
.




참
 
부
정
(
T
r
u
e
 
N
e
g
a
t
i
v
e
s
,
 
T
N
)
 
:
 
어
떤
 
관
측
치
가
 
특
정
 
클
래
스
에
 
속
하
지
 
않
는
다
고
 
예
측
하
고
 
실
제
로
 
그
 
클
래
스
에
 
속
하
지
 
않
을
 
때
 
참
 
부
정
이
라
고
 
합
니
다
.




거
짓
 
긍
정
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
,
 
F
P
)
 
:
 
어
떤
 
관
측
치
가
 
특
정
 
클
래
스
에
 
속
한
다
고
 
예
측
했
지
만
 
실
제
로
는
 
그
 
클
래
스
에
 
속
하
지
 
않
을
 
때
 
거
짓
 
긍
정
이
라
고
 
합
니
다
.
 
이
러
한
 
유
형
의
 
오
류
를
 
1
형
 
오
류
(
T
y
p
e
 
I
 
e
r
r
o
r
)
 
라
고
 
합
니
다
.




거
짓
 
부
정
(
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
,
 
F
N
)
 
:
 
어
떤
 
관
측
치
가
 
특
정
 
클
래
스
에
 
속
하
지
 
않
는
다
고
 
예
측
했
지
만
 
실
제
로
는
 
그
 
클
래
스
에
 
속
할
 
때
 
거
짓
 
부
정
이
라
고
 
합
니
다
.
 
이
는
 
매
우
 
심
각
한
 
오
류
로
서
 
2
형
 
오
류
(
T
y
p
e
 
I
I
 
e
r
r
o
r
)
 
라
고
 
합
니
다
.




이
 
네
 
가
지
 
결
과
는
 
아
래
와
 
같
은
 
혼
동
 
행
렬
에
 
요
약
됩
니
다
.



```python
#
 
P
r
i
n
t
 
t
h
e
 
C
o
n
f
u
s
i
o
n
 
M
a
t
r
i
x
 
a
n
d
 
s
l
i
c
e
 
i
t
 
i
n
t
o
 
f
o
u
r
 
p
i
e
c
e
s


f
r
o
m
 
s
k
l
e
a
r
n
.
m
e
t
r
i
c
s
 
i
m
p
o
r
t
 
c
o
n
f
u
s
i
o
n
_
m
a
t
r
i
x


c
m
 
=
 
c
o
n
f
u
s
i
o
n
_
m
a
t
r
i
x
(
y
_
t
e
s
t
,
 
y
_
p
r
e
d
_
t
e
s
t
)


p
r
i
n
t
(
'
C
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
\
n
\
n
'
,
 
c
m
)


p
r
i
n
t
(
'
\
n
T
r
u
e
 
P
o
s
i
t
i
v
e
s
(
T
P
)
 
=
 
'
,
 
c
m
[
0
,
0
]
)


p
r
i
n
t
(
'
\
n
T
r
u
e
 
N
e
g
a
t
i
v
e
s
(
T
N
)
 
=
 
'
,
 
c
m
[
1
,
1
]
)


p
r
i
n
t
(
'
\
n
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
(
F
P
)
 
=
 
'
,
 
c
m
[
0
,
1
]
)


p
r
i
n
t
(
'
\
n
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
(
F
N
)
 
=
 
'
,
 
c
m
[
1
,
0
]
)
```

<pre>
C
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x


 
[
[
2
1
5
4
3
 
 
1
1
8
3
]

 
[
 
3
2
2
7
 
 
3
1
3
9
]
]


T
r
u
e
 
P
o
s
i
t
i
v
e
s
(
T
P
)
 
=
 
 
2
1
5
4
3


T
r
u
e
 
N
e
g
a
t
i
v
e
s
(
T
N
)
 
=
 
 
3
1
3
9


F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
(
F
P
)
 
=
 
 
1
1
8
3


F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
(
F
N
)
 
=
 
 
3
2
2
7

</pre>
오
차
 
행
렬
(
c
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
)
은
 
2
1
5
4
3
 
+
 
3
1
3
9
 
=
 
 
2
4
6
8
2
개
의
 
정
확
한
 
예
측
과
 
3
2
2
7
 
+
 
1
1
8
3
 
=
 
4
4
1
0
개
의
 
부
정
확
한
 
예
측
을
 
보
여
줍
니
다
.




이
 
경
우
,
 
다
음
과
 
같
습
니
다
.




T
r
u
e
 
P
o
s
i
t
i
v
e
s
 
(
실
제
 
양
성
:
1
 
및
 
예
측
 
양
성
:
1
)
 
-
 
2
0
8
9
2




T
r
u
e
 
N
e
g
a
t
i
v
e
s
 
(
실
제
 
음
성
:
0
 
및
 
예
측
 
음
성
:
0
)
 
-
 
3
2
8
5




F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
 
(
실
제
 
음
성
:
0
이
지
만
 
예
측
 
양
성
:
1
)
 
-
 
1
1
7
5
 
(
1
형
 
오
류
)




F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
 
(
실
제
 
양
성
:
1
이
지
만
 
예
측
 
음
성
:
0
)
 
-
 
3
0
8
7
 
(
2
형
 
오
류
)



```python
#
 
v
i
s
u
a
l
i
z
e
 
c
o
n
f
u
s
i
o
n
 
m
a
t
r
i
x
 
w
i
t
h
 
s
e
a
b
o
r
n
 
h
e
a
t
m
a
p


c
m
_
m
a
t
r
i
x
 
=
 
p
d
.
D
a
t
a
F
r
a
m
e
(
d
a
t
a
=
c
m
,
 
c
o
l
u
m
n
s
=
[
'
A
c
t
u
a
l
 
P
o
s
i
t
i
v
e
:
1
'
,
 
'
A
c
t
u
a
l
 
N
e
g
a
t
i
v
e
:
0
'
]
,
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
d
e
x
=
[
'
P
r
e
d
i
c
t
 
P
o
s
i
t
i
v
e
:
1
'
,
 
'
P
r
e
d
i
c
t
 
N
e
g
a
t
i
v
e
:
0
'
]
)


s
n
s
.
h
e
a
t
m
a
p
(
c
m
_
m
a
t
r
i
x
,
 
a
n
n
o
t
=
T
r
u
e
,
 
f
m
t
=
'
d
'
,
 
c
m
a
p
=
'
Y
l
G
n
B
u
'
)
```

<pre>
<
m
a
t
p
l
o
t
l
i
b
.
a
x
e
s
.
_
s
u
b
p
l
o
t
s
.
A
x
e
s
S
u
b
p
l
o
t
 
a
t
 
0
x
7
5
6
b
b
b
0
c
a
b
e
0
>
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
2
 
A
x
e
s
>
</pre>
#
 
*
*
1
6
.
 
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
m
e
t
r
i
c
e
s
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
6
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)


#
#
 
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
R
e
p
o
r
t






*
*
분
류
 
보
고
서
(
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
R
e
p
o
r
t
)
*
*
는
 
분
류
 
모
델
의
 
성
능
을
 
평
가
하
는
 
다
른
 
방
법
입
니
다
.
 
이
는
 
모
델
의
 
정
밀
도
(
p
r
e
c
i
s
i
o
n
)
,
 
재
현
율
(
r
e
c
a
l
l
)
,
 
f
1
점
수
(
f
1
 
s
c
o
r
e
)
 
및
 
지
원
(
s
u
p
p
o
r
t
)
 
점
수
를
 
표
시
합
니
다
.
 
이
러
한
 
용
어
는
 
나
중
에
 
설
명
하
겠
습
니
다
.




분
류
 
보
고
서
를
 
출
력
하
는
 
방
법
은
 
다
음
과
 
같
습
니
다
:
-



```python
f
r
o
m
 
s
k
l
e
a
r
n
.
m
e
t
r
i
c
s
 
i
m
p
o
r
t
 
c
l
a
s
s
i
f
i
c
a
t
i
o
n
_
r
e
p
o
r
t


p
r
i
n
t
(
c
l
a
s
s
i
f
i
c
a
t
i
o
n
_
r
e
p
o
r
t
(
y
_
t
e
s
t
,
 
y
_
p
r
e
d
_
t
e
s
t
)
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
r
e
c
i
s
i
o
n
 
 
 
 
r
e
c
a
l
l
 
 
f
1
-
s
c
o
r
e
 
 
 
s
u
p
p
o
r
t


 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
.
8
7
 
 
 
 
 
 
0
.
9
5
 
 
 
 
 
 
0
.
9
1
 
 
 
 
 
2
2
7
2
6

 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
.
7
3
 
 
 
 
 
 
0
.
4
9
 
 
 
 
 
 
0
.
5
9
 
 
 
 
 
 
6
3
6
6


 
 
 
 
a
c
c
u
r
a
c
y
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
8
5
 
 
 
 
 
2
9
0
9
2

 
 
 
m
a
c
r
o
 
a
v
g
 
 
 
 
 
 
 
0
.
8
0
 
 
 
 
 
 
0
.
7
2
 
 
 
 
 
 
0
.
7
5
 
 
 
 
 
2
9
0
9
2

w
e
i
g
h
t
e
d
 
a
v
g
 
 
 
 
 
 
 
0
.
8
4
 
 
 
 
 
 
0
.
8
5
 
 
 
 
 
 
0
.
8
4
 
 
 
 
 
2
9
0
9
2


</pre>
#
#
 
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
a
c
c
u
r
a
c
y



```python
T
P
 
=
 
c
m
[
0
,
0
]

T
N
 
=
 
c
m
[
1
,
1
]

F
P
 
=
 
c
m
[
0
,
1
]

F
N
 
=
 
c
m
[
1
,
0
]
```


```python
#
 
p
r
i
n
t
 
c
l
a
s
s
i
f
i
c
a
t
i
o
n
 
a
c
c
u
r
a
c
y


c
l
a
s
s
i
f
i
c
a
t
i
o
n
_
a
c
c
u
r
a
c
y
 
=
 
(
T
P
 
+
 
T
N
)
 
/
 
f
l
o
a
t
(
T
P
 
+
 
T
N
 
+
 
F
P
 
+
 
F
N
)


p
r
i
n
t
(
'
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
a
c
c
u
r
a
c
y
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
c
l
a
s
s
i
f
i
c
a
t
i
o
n
_
a
c
c
u
r
a
c
y
)
)

```

<pre>
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
a
c
c
u
r
a
c
y
 
:
 
0
.
8
4
8
4

</pre>
#
#
 
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
e
r
r
o
r



```python
#
 
p
r
i
n
t
 
c
l
a
s
s
i
f
i
c
a
t
i
o
n
 
e
r
r
o
r


c
l
a
s
s
i
f
i
c
a
t
i
o
n
_
e
r
r
o
r
 
=
 
(
F
P
 
+
 
F
N
)
 
/
 
f
l
o
a
t
(
T
P
 
+
 
T
N
 
+
 
F
P
 
+
 
F
N
)


p
r
i
n
t
(
'
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
e
r
r
o
r
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
c
l
a
s
s
i
f
i
c
a
t
i
o
n
_
e
r
r
o
r
)
)

```

<pre>
C
l
a
s
s
i
f
i
c
a
t
i
o
n
 
e
r
r
o
r
 
:
 
0
.
1
5
1
6

</pre>
#
#
 
P
r
e
c
i
s
i
o
n






*
*
정
밀
도
 
(
P
r
e
c
i
s
i
o
n
)
*
*
 
는
 
예
측
된
 
양
성
 
결
과
 
중
에
서
 
올
바
르
게
 
예
측
된
 
비
율
로
 
정
의
될
 
수
 
있
습
니
다
.
 
이
는
 
참
 
양
성
(
T
r
u
e
 
P
o
s
i
t
i
v
e
,
 
T
P
)
의
 
수
를
 
참
 
양
성
과
 
거
짓
 
양
성
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
,
 
F
P
)
의
 
합
(
T
P
 
+
 
F
P
)
으
로
 
나
눈
 
비
율
로
 
표
현
할
 
수
 
있
습
니
다
.




따
라
서
 
정
밀
도
는
 
양
성
 
클
래
스
보
다
는
 
음
성
 
클
래
스
보
다
 
더
 
관
련
된
 
결
과
를
 
식
별
합
니
다
.




수
학
적
으
로
는
,
 
정
밀
도
는
 
`
T
P
 
/
 
(
T
P
 
+
 
F
P
)
`
 
로
 
정
의
될
 
수
 
있
습
니
다
.









```python
#
 
p
r
i
n
t
 
p
r
e
c
i
s
i
o
n
 
s
c
o
r
e


p
r
e
c
i
s
i
o
n
 
=
 
T
P
 
/
 
f
l
o
a
t
(
T
P
 
+
 
F
P
)



p
r
i
n
t
(
'
P
r
e
c
i
s
i
o
n
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
p
r
e
c
i
s
i
o
n
)
)

```

<pre>
P
r
e
c
i
s
i
o
n
 
:
 
0
.
9
4
7
9

</pre>
#
#
 
R
e
c
a
l
l






P
r
e
c
i
s
i
o
n
는
 
모
델
이
 
예
측
한
 
양
성
 
중
에
서
 
올
바
르
게
 
예
측
한
 
비
율
을
 
나
타
내
는
 
지
표
입
니
다
.
 
이
것
은
 
실
제
 
양
성
 
중
에
서
 
모
델
이
 
양
성
으
로
 
예
측
한
 
것
이
 
올
바
른
 
비
율
(
T
P
)
을
 
모
든
 
양
성
 
예
측
(
올
바
른
 
양
성
(
T
P
)
 
+
 
잘
못
된
 
양
성
(
F
P
)
)
으
로
 
나
눈
 
값
으
로
 
표
시
됩
니
다
.




즉
,
 
정
밀
도
는
 
양
성
 
클
래
스
에
 
대
해
서
만
 
음
성
 
클
래
스
보
다
 
더
 
관
심
이
 
있
으
며
,
 
정
확
하
게
 
예
측
된
 
양
성
 
비
율
을
 
식
별
합
니
다
.




수
학
적
으
로
,
 
정
밀
도
는
 
T
P
 
/
 
(
T
P
 
+
 
F
P
)
로
 
정
의
됩
니
다
.




R
e
c
a
l
l
 
또
는
 
민
감
도
는
 
모
델
이
 
예
측
한
 
양
성
 
결
과
에
서
 
실
제
 
양
성
 
결
과
의
 
비
율
로
 
정
의
될
 
수
 
있
습
니
다
.
 
이
것
은
 
실
제
 
양
성
 
중
에
서
 
모
델
이
 
실
제
로
 
양
성
으
로
 
예
측
한
 
것
(
T
P
)
을
 
실
제
 
양
성
(
T
P
 
+
 
F
N
)
으
로
 
나
눈
 
값
으
로
 
표
시
됩
니
다
.




수
학
적
으
로
,
 
민
감
도
는
 
T
P
 
/
 
(
T
P
 
+
 
F
N
)
으
로
 
정
의
됩
니
다
.











```python
r
e
c
a
l
l
 
=
 
T
P
 
/
 
f
l
o
a
t
(
T
P
 
+
 
F
N
)


p
r
i
n
t
(
'
R
e
c
a
l
l
 
o
r
 
S
e
n
s
i
t
i
v
i
t
y
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
r
e
c
a
l
l
)
)
```

<pre>
R
e
c
a
l
l
 
o
r
 
S
e
n
s
i
t
i
v
i
t
y
 
:
 
0
.
8
6
9
7

</pre>
#
#
 
T
r
u
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e






*
*
T
r
u
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
*
*
는
 
*
*
재
현
율
*
*
과
 
같
은
 
말
이
다



```python
t
r
u
e
_
p
o
s
i
t
i
v
e
_
r
a
t
e
 
=
 
T
P
 
/
 
f
l
o
a
t
(
T
P
 
+
 
F
N
)



p
r
i
n
t
(
'
T
r
u
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
t
r
u
e
_
p
o
s
i
t
i
v
e
_
r
a
t
e
)
)
```

<pre>
T
r
u
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
 
:
 
0
.
8
6
9
7

</pre>
#
#
 
F
a
l
s
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e



```python
f
a
l
s
e
_
p
o
s
i
t
i
v
e
_
r
a
t
e
 
=
 
F
P
 
/
 
f
l
o
a
t
(
F
P
 
+
 
T
N
)



p
r
i
n
t
(
'
F
a
l
s
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
f
a
l
s
e
_
p
o
s
i
t
i
v
e
_
r
a
t
e
)
)
```

<pre>
F
a
l
s
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
 
:
 
0
.
2
7
3
7

</pre>
#
#
 
S
p
e
c
i
f
i
c
i
t
y



```python
s
p
e
c
i
f
i
c
i
t
y
 
=
 
T
N
 
/
 
(
T
N
 
+
 
F
P
)


p
r
i
n
t
(
'
S
p
e
c
i
f
i
c
i
t
y
 
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
s
p
e
c
i
f
i
c
i
t
y
)
)
```

<pre>
S
p
e
c
i
f
i
c
i
t
y
 
:
 
0
.
7
2
6
3

</pre>
#
#
 
f
1
-
s
c
o
r
e






"
f
1
-
s
c
o
r
e
"
는
 
정
밀
도
(
P
r
e
c
i
s
i
o
n
)
와
 
재
현
율
(
R
e
c
a
l
l
)
의
 
가
중
치
 
조
화
 
평
균
(
w
e
i
g
h
t
e
d
 
h
a
r
m
o
n
i
c
 
m
e
a
n
)
입
니
다
.
 
최
상
의
 
"
f
1
-
s
c
o
r
e
"
는
 
1
.
0
이
고
,
 
최
악
의
 
경
우
는
 
0
.
0
입
니
다
.
 
"
f
1
-
s
c
o
r
e
"
는
 
정
밀
도
와
 
재
현
율
의
 
조
화
 
평
균
(
h
a
r
m
o
n
i
c
 
m
e
a
n
)
이
므
로
,
 
정
확
도
 
측
정
값
은
 
정
밀
도
와
 
재
현
율
을
 
포
함
하
여
 
계
산
되
기
 
때
문
에
 
항
상
 
더
 
높
은
 
값
을
 
가
집
니
다
.
 
분
류
 
모
델
을
 
비
교
할
 
때
는
 
"
f
1
-
s
c
o
r
e
"
의
 
가
중
 
평
균
(
w
e
i
g
h
t
e
d
 
a
v
e
r
a
g
e
)
을
 
사
용
해
야
 
하
며
,
 
전
체
적
인
 
정
확
도
보
다
는
 
더
 
나
은
 
비
교
 
지
표
가
 
됩
니
다
.






#
#
 
S
u
p
p
o
r
t






"
S
u
p
p
o
r
t
"
는
 
데
이
터
셋
에
서
 
클
래
스
가
 
실
제
로
 
발
생
한
 
횟
수
(
a
c
t
u
a
l
 
n
u
m
b
e
r
 
o
f
 
o
c
c
u
r
r
e
n
c
e
s
)
입
니
다
.


#
 
*
*
1
7
.
 
임
계
값
 
레
벨
 
조
정
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
7
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
#
 
p
r
i
n
t
 
t
h
e
 
f
i
r
s
t
 
1
0
 
p
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s
 
o
f
 
t
w
o
 
c
l
a
s
s
e
s
-
 
0
 
a
n
d
 
1


y
_
p
r
e
d
_
p
r
o
b
 
=
 
l
o
g
r
e
g
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
X
_
t
e
s
t
)
[
0
:
1
0
]


y
_
p
r
e
d
_
p
r
o
b
```

<pre>
a
r
r
a
y
(
[
[
0
.
8
3
2
1
8
0
1
2
,
 
0
.
1
6
7
8
1
9
8
8
]
,

 
 
 
 
 
 
 
[
0
.
7
4
5
4
7
8
9
7
,
 
0
.
2
5
4
5
2
1
0
3
]
,

 
 
 
 
 
 
 
[
0
.
7
9
8
6
4
8
9
9
,
 
0
.
2
0
1
3
5
1
0
1
]
,

 
 
 
 
 
 
 
[
0
.
5
8
5
0
9
2
1
3
,
 
0
.
4
1
4
9
0
7
8
7
]
,

 
 
 
 
 
 
 
[
0
.
9
2
1
6
5
7
8
4
,
 
0
.
0
7
8
3
4
2
1
6
]
,

 
 
 
 
 
 
 
[
0
.
9
5
6
2
5
8
7
9
,
 
0
.
0
4
3
7
4
1
2
1
]
,

 
 
 
 
 
 
 
[
0
.
5
7
8
8
1
8
8
8
,
 
0
.
4
2
1
1
8
1
1
2
]
,

 
 
 
 
 
 
 
[
0
.
5
0
2
9
3
9
1
6
,
 
0
.
4
9
7
0
6
0
8
4
]
,

 
 
 
 
 
 
 
[
0
.
8
0
2
8
1
9
4
3
,
 
0
.
1
9
7
1
8
0
5
7
]
,

 
 
 
 
 
 
 
[
0
.
7
2
3
4
0
9
4
6
,
 
0
.
2
7
6
5
9
0
5
4
]
]
)
</pre>
#
#
#
 
O
b
s
e
r
v
a
t
i
o
n
s






-
 
각
 
행
마
다
 
숫
자
의
 
합
은
 
1
이
 
됩
니
다
.




-
 
0
과
 
1
 
두
 
개
의
 
클
래
스
에
 
해
당
하
는
 
2
개
의
 
열
이
 
있
습
니
다
.




 
 
 
 
-
 
클
래
스
 
0
 
-
 
내
일
 
비
가
 
오
지
 
않
을
 
확
률
을
 
예
측
한
 
확
률
 
값




 
 
 
 
-
 
클
래
스
 
1
 
-
 
내
일
 
비
가
 
올
 
확
률
을
 
예
측
한
 
확
률
 
값




-
 
예
측
된
 
확
률
 
값
의
 
중
요
성




 
 
 
 
-
 
확
률
 
값
에
 
따
라
 
각
 
관
측
치
를
 
내
일
 
비
가
 
올
 
확
률
이
 
높
은
 
순
으
로
 
순
위
를
 
매
길
 
수
 
있
습
니
다
.
 


-
 
p
r
e
d
i
c
t
_
p
r
o
b
a
 
과
정




 
 
 
 
-
 
각
 
클
래
스
의
 
확
률
 
값
을
 
예
측
합
니
다
.




 
 
 
 
-
 
가
장
 
높
은
 
확
률
 
값
을
 
가
진
 
클
래
스
를
 
선
택
합
니
다
.




-
 
분
류
 
임
계
값




 
 
 
 
-
 
분
류
 
임
계
값
이
 
0
.
5
로
 
설
정
되
어
 
있
습
니
다
.




 
 
 
 
-
 
클
래
스
 
1
은
 
확
률
 
값
이
 
0
.
5
보
다
 
크
면
 
내
일
 
비
가
 
올
 
확
률
로
 
예
측
됩
니
다
.




 
 
 
 
-
 
클
래
스
 
0
은
 
확
률
 
값
이
 
0
.
5
보
다
 
작
으
면
 
내
일
 
비
가
 
오
지
 
않
을
 
확
률
로
 
예
측
됩
니
다
.





```python
#
 
s
t
o
r
e
 
t
h
e
 
p
r
o
b
a
b
i
l
i
t
i
e
s
 
i
n
 
d
a
t
a
f
r
a
m
e


y
_
p
r
e
d
_
p
r
o
b
_
d
f
 
=
 
p
d
.
D
a
t
a
F
r
a
m
e
(
d
a
t
a
=
y
_
p
r
e
d
_
p
r
o
b
,
 
c
o
l
u
m
n
s
=
[
'
P
r
o
b
 
o
f
 
-
 
N
o
 
r
a
i
n
 
t
o
m
o
r
r
o
w
 
(
0
)
'
,
 
'
P
r
o
b
 
o
f
 
-
 
R
a
i
n
 
t
o
m
o
r
r
o
w
 
(
1
)
'
]
)


y
_
p
r
e
d
_
p
r
o
b
_
d
f
```

<pre>
 
 
 
P
r
o
b
 
o
f
 
-
 
N
o
 
r
a
i
n
 
t
o
m
o
r
r
o
w
 
(
0
)
 
 
P
r
o
b
 
o
f
 
-
 
R
a
i
n
 
t
o
m
o
r
r
o
w
 
(
1
)

0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
8
3
2
1
8
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
1
6
7
8
2
0

1
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
7
4
5
4
7
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
5
4
5
2
1

2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
7
9
8
6
4
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
0
1
3
5
1

3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
8
5
0
9
2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
4
1
4
9
0
8

4
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
9
2
1
6
5
8
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
7
8
3
4
2

5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
9
5
6
2
5
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
4
3
7
4
1

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
7
8
8
1
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
4
2
1
1
8
1

7
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
0
2
9
3
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
4
9
7
0
6
1

8
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
8
0
2
8
1
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
1
9
7
1
8
1

9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
7
2
3
4
0
9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
7
6
5
9
1
</pre>

```python
#
 
p
r
i
n
t
 
t
h
e
 
f
i
r
s
t
 
1
0
 
p
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s
 
f
o
r
 
c
l
a
s
s
 
1
 
-
 
P
r
o
b
a
b
i
l
i
t
y
 
o
f
 
r
a
i
n


l
o
g
r
e
g
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
X
_
t
e
s
t
)
[
0
:
1
0
,
 
1
]
```

<pre>
a
r
r
a
y
(
[
0
.
1
6
7
8
1
9
8
8
,
 
0
.
2
5
4
5
2
1
0
3
,
 
0
.
2
0
1
3
5
1
0
1
,
 
0
.
4
1
4
9
0
7
8
7
,
 
0
.
0
7
8
3
4
2
1
6
,

 
 
 
 
 
 
 
0
.
0
4
3
7
4
1
2
1
,
 
0
.
4
2
1
1
8
1
1
2
,
 
0
.
4
9
7
0
6
0
8
4
,
 
0
.
1
9
7
1
8
0
5
7
,
 
0
.
2
7
6
5
9
0
5
4
]
)
</pre>

```python
#
 
s
t
o
r
e
 
t
h
e
 
p
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s
 
f
o
r
 
c
l
a
s
s
 
1
 
-
 
P
r
o
b
a
b
i
l
i
t
y
 
o
f
 
r
a
i
n


y
_
p
r
e
d
1
 
=
 
l
o
g
r
e
g
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
X
_
t
e
s
t
)
[
:
,
 
1
]
```


```python
#
 
p
l
o
t
 
h
i
s
t
o
g
r
a
m
 
o
f
 
p
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s



#
 
a
d
j
u
s
t
 
t
h
e
 
f
o
n
t
 
s
i
z
e
 

p
l
t
.
r
c
P
a
r
a
m
s
[
'
f
o
n
t
.
s
i
z
e
'
]
 
=
 
1
2



#
 
p
l
o
t
 
h
i
s
t
o
g
r
a
m
 
w
i
t
h
 
1
0
 
b
i
n
s

p
l
t
.
h
i
s
t
(
y
_
p
r
e
d
1
,
 
b
i
n
s
 
=
 
1
0
)



#
 
s
e
t
 
t
h
e
 
t
i
t
l
e
 
o
f
 
p
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s

p
l
t
.
t
i
t
l
e
(
'
H
i
s
t
o
g
r
a
m
 
o
f
 
p
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s
 
o
f
 
r
a
i
n
'
)



#
 
s
e
t
 
t
h
e
 
x
-
a
x
i
s
 
l
i
m
i
t

p
l
t
.
x
l
i
m
(
0
,
1
)



#
 
s
e
t
 
t
h
e
 
t
i
t
l
e

p
l
t
.
x
l
a
b
e
l
(
'
P
r
e
d
i
c
t
e
d
 
p
r
o
b
a
b
i
l
i
t
i
e
s
 
o
f
 
r
a
i
n
'
)

p
l
t
.
y
l
a
b
e
l
(
'
F
r
e
q
u
e
n
c
y
'
)
```

<pre>
T
e
x
t
(
0
,
 
0
.
5
,
 
'
F
r
e
q
u
e
n
c
y
'
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>
#
#
#
 
조
사
결
과




-
 
위
의
 
히
스
토
그
램
은
 
매
우
 
양
의
 
왜
도
(
s
k
e
w
e
d
)
를
 
가
진
 
것
으
로
 
보
입
니
다
.




-
 
첫
 
번
째
 
열
은
 
0
.
0
과
 
0
.
1
 
사
이
의
 
확
률
 
값
을
 
가
진
 
약
 
1
5
0
0
0
개
의
 
관
측
치
가
 
있
음
을
 
나
타
냅
니
다
.




-
 
0
.
5
보
다
 
큰
 
확
률
 
값
을
 
가
진
 
관
측
치
는
 
적
습
니
다
.




-
 
따
라
서
 
이
 
적
은
 
수
의
 
관
측
치
는
 
내
일
 
비
가
 
올
 
확
률
로
 
예
측
됩
니
다
.




-
 
대
부
분
의
 
관
측
치
는
 
내
일
 
비
가
 
오
지
 
않
을
 
확
률
로
 
예
측
됩
니
다
.


#
#
#
 
L
o
w
e
r
 
t
h
e
 
t
h
r
e
s
h
o
l
d



```python
f
r
o
m
 
s
k
l
e
a
r
n
.
p
r
e
p
r
o
c
e
s
s
i
n
g
 
i
m
p
o
r
t
 
b
i
n
a
r
i
z
e


f
o
r
 
i
 
i
n
 
r
a
n
g
e
(
1
,
 
5
)
:

 
 
 
 
c
m
1
 
=
 
0

 
 
 
 
y
_
p
r
e
d
1
 
=
 
l
o
g
r
e
g
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
X
_
t
e
s
t
)
[
:
,
 
1
]

 
 
 
 
y
_
p
r
e
d
1
 
=
 
y
_
p
r
e
d
1
.
r
e
s
h
a
p
e
(
-
1
,
 
1
)

 
 
 
 
y
_
p
r
e
d
2
 
=
 
b
i
n
a
r
i
z
e
(
y
_
p
r
e
d
1
,
 
i
/
1
0
)

 
 
 
 
y
_
p
r
e
d
2
 
=
 
n
p
.
w
h
e
r
e
(
y
_
p
r
e
d
2
 
=
=
 
1
,
 
'
Y
e
s
'
,
 
'
N
o
'
)

 
 
 
 

 
 
 
 
y
_
t
e
s
t
_
s
t
r
 
=
 
n
p
.
w
h
e
r
e
(
y
_
t
e
s
t
 
=
=
 
1
,
 
'
Y
e
s
'
,
 
'
N
o
'
)
 
#
 
y
_
t
e
s
t
 
레
이
블
을
 
문
자
열
 
형
식
으
로
 
변
환

 
 
 
 

 
 
 
 
c
m
1
 
=
 
c
o
n
f
u
s
i
o
n
_
m
a
t
r
i
x
(
y
_
t
e
s
t
_
s
t
r
,
 
y
_
p
r
e
d
2
)

 
 
 
 

 
 
 
 
p
r
i
n
t
(
'
W
i
t
h
'
,
 
i
/
1
0
,
 
'
t
h
r
e
s
h
o
l
d
 
t
h
e
 
C
o
n
f
u
s
i
o
n
 
M
a
t
r
i
x
 
i
s
\
n
\
n
'
,
 
c
m
1
,
 
'
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
'
w
i
t
h
'
,
 
c
m
1
[
0
,
0
]
+
c
m
1
[
1
,
1
]
,
 
'
c
o
r
r
e
c
t
 
p
r
e
d
i
c
t
i
o
n
s
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
c
m
1
[
0
,
1
]
,
 
'
T
y
p
e
 
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
)
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
c
m
1
[
1
,
0
]
,
 
'
T
y
p
e
 
I
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
)
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
'
A
c
c
u
r
a
c
y
 
s
c
o
r
e
:
'
,
 
a
c
c
u
r
a
c
y
_
s
c
o
r
e
(
y
_
t
e
s
t
_
s
t
r
,
 
y
_
p
r
e
d
2
)
,
 
'
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
'
S
e
n
s
i
t
i
v
i
t
y
:
'
,
 
c
m
1
[
1
,
1
]
/
f
l
o
a
t
(
c
m
1
[
1
,
1
]
+
c
m
1
[
1
,
0
]
)
,
 
'
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
'
S
p
e
c
i
f
i
c
i
t
y
:
'
,
 
c
m
1
[
0
,
0
]
/
f
l
o
a
t
(
c
m
1
[
0
,
0
]
+
c
m
1
[
0
,
1
]
)
,
 
'
\
n
\
n
'
,

 
 
 
 
 
 
 
 
 
 
'
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
\
n
\
n
'
)

```

<pre>
W
i
t
h
 
0
.
1
 
t
h
r
e
s
h
o
l
d
 
t
h
e
 
C
o
n
f
u
s
i
o
n
 
M
a
t
r
i
x
 
i
s


 
[
[
1
3
2
9
2
 
 
9
4
3
4
]

 
[
 
 
5
7
1
 
 
5
7
9
5
]
]
 


 
w
i
t
h
 
1
9
0
8
7
 
c
o
r
r
e
c
t
 
p
r
e
d
i
c
t
i
o
n
s


 
9
4
3
4
 
T
y
p
e
 
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
)


 
5
7
1
 
T
y
p
e
 
I
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
)


 
A
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
6
5
6
0
9
1
0
2
1
5
8
6
6
9
0
5
 


 
S
e
n
s
i
t
i
v
i
t
y
:
 
0
.
9
1
0
3
0
4
7
4
3
9
5
2
2
4
6
3
 


 
S
p
e
c
i
f
i
c
i
t
y
:
 
0
.
5
8
4
8
8
0
7
5
3
3
2
2
1
8
6
 


 
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=



W
i
t
h
 
0
.
2
 
t
h
r
e
s
h
o
l
d
 
t
h
e
 
C
o
n
f
u
s
i
o
n
 
M
a
t
r
i
x
 
i
s


 
[
[
1
7
7
4
1
 
 
4
9
8
5
]

 
[
 
1
3
6
5
 
 
5
0
0
1
]
]
 


 
w
i
t
h
 
2
2
7
4
2
 
c
o
r
r
e
c
t
 
p
r
e
d
i
c
t
i
o
n
s


 
4
9
8
5
 
T
y
p
e
 
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
)


 
1
3
6
5
 
T
y
p
e
 
I
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
)


 
A
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
7
8
1
7
2
6
9
3
5
2
3
9
9
2
8
5
 


 
S
e
n
s
i
t
i
v
i
t
y
:
 
0
.
7
8
5
5
7
9
6
4
1
8
4
7
3
1
3
9
 


 
S
p
e
c
i
f
i
c
i
t
y
:
 
0
.
7
8
0
6
4
7
7
1
6
2
7
2
1
1
1
3
 


 
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=



W
i
t
h
 
0
.
3
 
t
h
r
e
s
h
o
l
d
 
t
h
e
 
C
o
n
f
u
s
i
o
n
 
M
a
t
r
i
x
 
i
s


 
[
[
1
9
7
4
4
 
 
2
9
8
2
]

 
[
 
2
0
4
3
 
 
4
3
2
3
]
]
 


 
w
i
t
h
 
2
4
0
6
7
 
c
o
r
r
e
c
t
 
p
r
e
d
i
c
t
i
o
n
s


 
2
9
8
2
 
T
y
p
e
 
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
)


 
2
0
4
3
 
T
y
p
e
 
I
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
)


 
A
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
8
2
7
2
7
2
1
0
2
2
9
6
1
6
3
9
 


 
S
e
n
s
i
t
i
v
i
t
y
:
 
0
.
6
7
9
0
7
6
3
4
3
0
7
2
5
7
3
 


 
S
p
e
c
i
f
i
c
i
t
y
:
 
0
.
8
6
8
7
8
4
6
5
1
9
4
0
5
0
8
7
 


 
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=



W
i
t
h
 
0
.
4
 
t
h
r
e
s
h
o
l
d
 
t
h
e
 
C
o
n
f
u
s
i
o
n
 
M
a
t
r
i
x
 
i
s


 
[
[
2
0
8
4
0
 
 
1
8
8
6
]

 
[
 
2
6
4
6
 
 
3
7
2
0
]
]
 


 
w
i
t
h
 
2
4
5
6
0
 
c
o
r
r
e
c
t
 
p
r
e
d
i
c
t
i
o
n
s


 
1
8
8
6
 
T
y
p
e
 
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
P
o
s
i
t
i
v
e
s
)


 
2
6
4
6
 
T
y
p
e
 
I
I
 
e
r
r
o
r
s
 
(
F
a
l
s
e
 
N
e
g
a
t
i
v
e
s
)


 
A
c
c
u
r
a
c
y
 
s
c
o
r
e
:
 
0
.
8
4
4
2
1
8
3
4
1
8
1
2
1
8
2
 


 
S
e
n
s
i
t
i
v
i
t
y
:
 
0
.
5
8
4
3
5
4
3
8
2
6
5
7
8
7
 


 
S
p
e
c
i
f
i
c
i
t
y
:
 
0
.
9
1
7
0
1
1
3
5
2
6
3
5
7
4
7
6
 


 
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=



</pre>
#
#
#
 
C
o
m
m
e
n
t
s






-
 
이
진
(
b
i
n
a
r
y
)
 
문
제
에
서
는
,
 
예
측
된
 
확
률
 
값
을
 
클
래
스
 
예
측
으
로
 
변
환
하
기
 
위
해
 
기
본
적
으
로
 
0
.
5
의
 
임
계
값
을
 
사
용
합
니
다
.




-
 
민
감
도
 
또
는
 
특
이
도
를
 
증
가
시
키
기
 
위
해
 
임
계
값
을
 
조
정
할
 
수
 
있
습
니
다
.




-
 
민
감
도
와
 
특
이
도
는
 
역
의
 
관
계
를
 
가
집
니
다
.
 
하
나
를
 
증
가
시
키
면
 
다
른
 
하
나
는
 
항
상
 
감
소
하
게
 
됩
니
다
.




-
 
임
계
값
을
 
높
이
면
 
정
확
도
가
 
증
가
하
는
 
것
을
 
볼
 
수
 
있
습
니
다
.




-
 
임
계
값
을
 
조
정
하
는
 
것
은
 
모
델
 
구
축
 
과
정
에
서
 
마
지
막
 
단
계
 
중
 
하
나
여
야
 
합
니
다
.


#
 
*
*
1
8
.
 
R
O
C
 
-
 
A
U
C
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
8
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)








#
#
 
R
O
C
 
곡
선


분
류
 
모
델
 
성
능
을
 
시
각
적
으
로
 
측
정
하
는
 
또
 
다
른
 
도
구
는
 
R
O
C
(
R
e
c
e
i
v
e
r
 
O
p
e
r
a
t
i
n
g
 
C
h
a
r
a
c
t
e
r
i
s
t
i
c
)
 
곡
선
입
니
다
.
 
R
O
C
 
곡
선
은
 
분
류
 
모
델
의
 
성
능
을
 
다
양
한
 
분
류
 
임
계
값
(
t
h
r
e
s
h
o
l
d
)
 
수
준
에
서
 
보
여
주
는
 
그
래
프
입
니
다
.




R
O
C
 
곡
선
은
 
다
양
한
 
임
계
값
에
서
 
*
*
진
짜
 
양
성
 
비
율
(
T
P
R
,
 
T
r
u
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
)
*
*
과
 
*
*
거
짓
 
양
성
 
비
율
(
F
P
R
,
 
F
a
l
s
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
)
*
*
을
 
나
타
냅
니
다
.




*
*
진
짜
 
양
성
 
비
율
(
T
P
R
)
*
*
은
 
민
감
도
(
R
e
c
a
l
l
)
로
도
 
불
립
니
다
.
 
이
는
 
T
P
 
/
 
(
T
P
 
+
 
F
N
)
의
 
비
율
로
 
정
의
됩
니
다
.




*
*
거
짓
 
양
성
 
비
율
(
F
P
R
)
*
*
은
 
F
P
 
/
 
(
F
P
 
+
 
T
N
)
의
 
비
율
로
 
정
의
됩
니
다
.




R
O
C
 
곡
선
에
서
는
 
단
일
 
지
점
의
 
T
P
R
(
진
짜
 
양
성
 
비
율
)
 
및
 
F
P
R
(
거
짓
 
양
성
 
비
율
)
에
 
초
점
을
 
맞
춥
니
다
.
 
이
를
 
통
해
 
다
양
한
 
분
류
 
임
계
값
 
수
준
에
서
 
T
P
R
 
및
 
F
P
R
로
 
이
루
어
진
 
R
O
C
 
곡
선
의
 
전
반
적
인
 
성
능
을
 
파
악
할
 
수
 
있
습
니
다
.
 
따
라
서
 
R
O
C
 
곡
선
은
 
다
양
한
 
분
류
 
임
계
값
 
수
준
에
서
 
T
P
R
 
대
 
F
P
R
을
 
나
타
냅
니
다
.
 
임
계
값
을
 
낮
추
면
 
더
 
많
은
 
항
목
이
 
양
성
으
로
 
분
류
될
 
수
 
있
습
니
다
.
 
이
는
 
진
짜
 
양
성
(
T
P
)
과
 
거
짓
 
양
성
(
F
P
)
을
 
모
두
 
증
가
시
킬
 
수
 
있
습
니
다
.





```python
#
 
p
l
o
t
 
R
O
C
 
C
u
r
v
e

f
r
o
m
 
s
k
l
e
a
r
n
.
m
e
t
r
i
c
s
 
i
m
p
o
r
t
 
r
o
c
_
c
u
r
v
e


#
 
y
_
t
e
s
t
와
 
y
_
p
r
e
d
1
을
 
계
산
한
 
후
에
 
R
O
C
 
곡
선
을
 
그
립
니
다
.

f
p
r
,
 
t
p
r
,
 
t
h
r
e
s
h
o
l
d
s
 
=
 
r
o
c
_
c
u
r
v
e
(
y
_
t
e
s
t
,
 
y
_
p
r
e
d
1
,
 
p
o
s
_
l
a
b
e
l
=
1
)


p
l
t
.
f
i
g
u
r
e
(
f
i
g
s
i
z
e
=
(
6
,
4
)
)

p
l
t
.
p
l
o
t
(
f
p
r
,
 
t
p
r
,
 
l
i
n
e
w
i
d
t
h
=
2
)

p
l
t
.
p
l
o
t
(
[
0
,
1
]
,
 
[
0
,
1
]
,
 
'
k
-
-
'
 
)

p
l
t
.
r
c
P
a
r
a
m
s
[
'
f
o
n
t
.
s
i
z
e
'
]
 
=
 
1
2

p
l
t
.
t
i
t
l
e
(
'
R
O
C
 
c
u
r
v
e
 
f
o
r
 
R
a
i
n
T
o
m
o
r
r
o
w
 
c
l
a
s
s
i
f
i
e
r
'
)

p
l
t
.
x
l
a
b
e
l
(
'
F
a
l
s
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
 
(
1
 
-
 
S
p
e
c
i
f
i
c
i
t
y
)
'
)

p
l
t
.
y
l
a
b
e
l
(
'
T
r
u
e
 
P
o
s
i
t
i
v
e
 
R
a
t
e
 
(
S
e
n
s
i
t
i
v
i
t
y
)
'
)

p
l
t
.
s
h
o
w
(
)


```

<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>
R
O
C
 
곡
선
은
 
특
정
 
문
맥
에
서
 
민
감
도
와
 
특
이
도
를
 
균
형
있
게
 
조
절
하
는
 
임
계
값
을
 
선
택
하
는
 
데
 
도
움
을
 
줍
니
다
.


#
#
 
R
O
C
-
A
U
C


 
R
O
C
-
A
U
C
는
 
R
e
c
e
i
v
e
r
 
O
p
e
r
a
t
i
n
g
 
C
h
a
r
a
c
t
e
r
i
s
t
i
c
 
-
 
A
r
e
a
 
U
n
d
e
r
 
C
u
r
v
e
의
 
약
어
로
,
 
분
류
기
의
 
성
능
을
 
비
교
하
는
 
기
술
입
니
다
.
 
이
 
기
술
에
서
는
 
곡
선
 
아
래
 
면
적
(
A
U
C
)
을
 
측
정
합
니
다
.
 
완
벽
한
 
분
류
기
는
 
R
O
C
 
A
U
C
가
 
1
이
 
되
고
,
 
완
전
한
 
랜
덤
 
분
류
기
는
 
R
O
C
 
A
U
C
가
 
0
.
5
가
 
됩
니
다
.




따
라
서
 
R
O
C
 
A
U
C
는
 
R
O
C
 
곡
선
 
아
래
의
 
면
적
의
 
백
분
율
입
니
다
.



```python
#
 
c
o
m
p
u
t
e
 
R
O
C
 
A
U
C


f
r
o
m
 
s
k
l
e
a
r
n
.
m
e
t
r
i
c
s
 
i
m
p
o
r
t
 
r
o
c
_
a
u
c
_
s
c
o
r
e


R
O
C
_
A
U
C
 
=
 
r
o
c
_
a
u
c
_
s
c
o
r
e
(
y
_
t
e
s
t
,
 
y
_
p
r
e
d
1
)


p
r
i
n
t
(
'
R
O
C
 
A
U
C
 
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
R
O
C
_
A
U
C
)
)
```

<pre>
R
O
C
 
A
U
C
 
:
 
0
.
8
6
7
1

</pre>
#
#
#
 
C
o
m
m
e
n
t
s




R
O
C
 
A
U
C
는
 
분
류
기
 
성
능
의
 
단
일
 
숫
자
 
요
약
입
니
다
.
 
값
이
 
높
을
수
록
 
분
류
기
가
 
더
 
좋
습
니
다
.




우
리
 
모
델
의
 
R
O
C
 
A
U
C
 
값
은
 
1
에
 
가
까
워
지
므
로
,
 
우
리
 
분
류
기
가
 
내
일
 
비
가
 
올
지
 
여
부
를
 
예
측
하
는
 
데
 
잘
 
동
작
한
다
고
 
결
론
을
 
내
릴
 
수
 
있
습
니
다
.



```python
#
 
c
a
l
c
u
l
a
t
e
 
c
r
o
s
s
-
v
a
l
i
d
a
t
e
d
 
R
O
C
 
A
U
C
 


f
r
o
m
 
s
k
l
e
a
r
n
.
m
o
d
e
l
_
s
e
l
e
c
t
i
o
n
 
i
m
p
o
r
t
 
c
r
o
s
s
_
v
a
l
_
s
c
o
r
e


C
r
o
s
s
_
v
a
l
i
d
a
t
e
d
_
R
O
C
_
A
U
C
 
=
 
c
r
o
s
s
_
v
a
l
_
s
c
o
r
e
(
l
o
g
r
e
g
,
 
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
c
v
=
5
,
 
s
c
o
r
i
n
g
=
'
r
o
c
_
a
u
c
'
)
.
m
e
a
n
(
)


p
r
i
n
t
(
'
C
r
o
s
s
 
v
a
l
i
d
a
t
e
d
 
R
O
C
 
A
U
C
 
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
C
r
o
s
s
_
v
a
l
i
d
a
t
e
d
_
R
O
C
_
A
U
C
)
)
```

<pre>
C
r
o
s
s
 
v
a
l
i
d
a
t
e
d
 
R
O
C
 
A
U
C
 
:
 
0
.
8
6
7
5

</pre>
#
 
*
*
1
9
.
 
k
-
F
o
l
d
 
C
r
o
s
s
 
V
a
l
i
d
a
t
i
o
n
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
1
9
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
#
 
A
p
p
l
y
i
n
g
 
5
-
F
o
l
d
 
C
r
o
s
s
 
V
a
l
i
d
a
t
i
o
n


f
r
o
m
 
s
k
l
e
a
r
n
.
m
o
d
e
l
_
s
e
l
e
c
t
i
o
n
 
i
m
p
o
r
t
 
c
r
o
s
s
_
v
a
l
_
s
c
o
r
e


s
c
o
r
e
s
 
=
 
c
r
o
s
s
_
v
a
l
_
s
c
o
r
e
(
l
o
g
r
e
g
,
 
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
c
v
 
=
 
5
,
 
s
c
o
r
i
n
g
=
'
a
c
c
u
r
a
c
y
'
)


p
r
i
n
t
(
'
C
r
o
s
s
-
v
a
l
i
d
a
t
i
o
n
 
s
c
o
r
e
s
:
{
}
'
.
f
o
r
m
a
t
(
s
c
o
r
e
s
)
)
```

<pre>
C
r
o
s
s
-
v
a
l
i
d
a
t
i
o
n
 
s
c
o
r
e
s
:
[
0
.
8
4
8
0
3
4
3
7
 
0
.
8
4
9
3
5
9
8
 
 
0
.
8
4
9
3
9
6
3
 
 
0
.
8
4
5
0
1
3
5
3
 
0
.
8
4
8
7
9
4
7
4
]

</pre>
교
차
 
검
증
 
정
확
도
를
 
요
약
하
려
면
,
 
해
당
 
정
확
도
의
 
평
균
을
 
계
산
할
 
수
 
있
습
니
다



```python
#
 
c
o
m
p
u
t
e
 
A
v
e
r
a
g
e
 
c
r
o
s
s
-
v
a
l
i
d
a
t
i
o
n
 
s
c
o
r
e


p
r
i
n
t
(
'
A
v
e
r
a
g
e
 
c
r
o
s
s
-
v
a
l
i
d
a
t
i
o
n
 
s
c
o
r
e
:
 
{
:
.
4
f
}
'
.
f
o
r
m
a
t
(
s
c
o
r
e
s
.
m
e
a
n
(
)
)
)
```

<pre>
A
v
e
r
a
g
e
 
c
r
o
s
s
-
v
a
l
i
d
a
t
i
o
n
 
s
c
o
r
e
:
 
0
.
8
4
8
1

</pre>
우
리
의
 
원
래
 
모
델
 
점
수
는
 
0
.
8
4
8
4
으
로
 
나
타
났
습
니
다
.
 
평
균
 
교
차
 
검
증
 
점
수
는
 
0
.
8
4
8
1
입
니
다
.
 
따
라
서
 
교
차
 
검
증
은
 
성
능
 
향
상
을
 
가
져
오
지
 
않
음
을
 
결
론
지
을
 
수
 
있
습
니
다
.


#
 
*
*
2
0
.
 
H
y
p
e
r
p
a
r
a
m
e
t
e
r
 
O
p
t
i
m
i
z
a
t
i
o
n
 
u
s
i
n
g
 
G
r
i
d
S
e
a
r
c
h
 
C
V
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
2
0
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)



```python
f
r
o
m
 
s
k
l
e
a
r
n
.
m
o
d
e
l
_
s
e
l
e
c
t
i
o
n
 
i
m
p
o
r
t
 
G
r
i
d
S
e
a
r
c
h
C
V



p
a
r
a
m
e
t
e
r
s
 
=
 
[
{
'
p
e
n
a
l
t
y
'
:
[
'
l
1
'
,
'
l
2
'
]
}
,
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
{
'
C
'
:
[
1
,
 
1
0
,
 
1
0
0
,
 
1
0
0
0
]
}
]




g
r
i
d
_
s
e
a
r
c
h
 
=
 
G
r
i
d
S
e
a
r
c
h
C
V
(
e
s
t
i
m
a
t
o
r
 
=
 
l
o
g
r
e
g
,
 
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
r
a
m
_
g
r
i
d
 
=
 
p
a
r
a
m
e
t
e
r
s
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
s
c
o
r
i
n
g
 
=
 
'
a
c
c
u
r
a
c
y
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
v
 
=
 
5
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
v
e
r
b
o
s
e
=
0
)



g
r
i
d
_
s
e
a
r
c
h
.
f
i
t
(
X
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
)

```

<pre>
G
r
i
d
S
e
a
r
c
h
C
V
(
c
v
=
5
,
 
e
r
r
o
r
_
s
c
o
r
e
=
'
r
a
i
s
e
-
d
e
p
r
e
c
a
t
i
n
g
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
e
s
t
i
m
a
t
o
r
=
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
1
.
0
,
 
c
l
a
s
s
_
w
e
i
g
h
t
=
N
o
n
e
,
 
d
u
a
l
=
F
a
l
s
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
i
t
_
i
n
t
e
r
c
e
p
t
=
T
r
u
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
e
r
c
e
p
t
_
s
c
a
l
i
n
g
=
1
,
 
l
1
_
r
a
t
i
o
=
N
o
n
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
a
x
_
i
t
e
r
=
1
0
0
,
 
m
u
l
t
i
_
c
l
a
s
s
=
'
w
a
r
n
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
n
_
j
o
b
s
=
N
o
n
e
,
 
p
e
n
a
l
t
y
=
'
l
2
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
t
o
l
=
0
.
0
0
0
1
,
 
v
e
r
b
o
s
e
=
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
w
a
r
m
_
s
t
a
r
t
=
F
a
l
s
e
)
,

 
 
 
 
 
 
 
 
 
 
 
 
 
i
i
d
=
'
w
a
r
n
'
,
 
n
_
j
o
b
s
=
N
o
n
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
r
a
m
_
g
r
i
d
=
[
{
'
p
e
n
a
l
t
y
'
:
 
[
'
l
1
'
,
 
'
l
2
'
]
}
,
 
{
'
C
'
:
 
[
1
,
 
1
0
,
 
1
0
0
,
 
1
0
0
0
]
}
]
,

 
 
 
 
 
 
 
 
 
 
 
 
 
p
r
e
_
d
i
s
p
a
t
c
h
=
'
2
*
n
_
j
o
b
s
'
,
 
r
e
f
i
t
=
T
r
u
e
,
 
r
e
t
u
r
n
_
t
r
a
i
n
_
s
c
o
r
e
=
F
a
l
s
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
s
c
o
r
i
n
g
=
'
a
c
c
u
r
a
c
y
'
,
 
v
e
r
b
o
s
e
=
0
)
</pre>

```python
#
 
e
x
a
m
i
n
e
 
t
h
e
 
b
e
s
t
 
m
o
d
e
l


#
 
b
e
s
t
 
s
c
o
r
e
 
a
c
h
i
e
v
e
d
 
d
u
r
i
n
g
 
t
h
e
 
G
r
i
d
S
e
a
r
c
h
C
V

p
r
i
n
t
(
'
G
r
i
d
S
e
a
r
c
h
 
C
V
 
b
e
s
t
 
s
c
o
r
e
 
:
 
{
:
.
4
f
}
\
n
\
n
'
.
f
o
r
m
a
t
(
g
r
i
d
_
s
e
a
r
c
h
.
b
e
s
t
_
s
c
o
r
e
_
)
)


#
 
p
r
i
n
t
 
p
a
r
a
m
e
t
e
r
s
 
t
h
a
t
 
g
i
v
e
 
t
h
e
 
b
e
s
t
 
r
e
s
u
l
t
s

p
r
i
n
t
(
'
P
a
r
a
m
e
t
e
r
s
 
t
h
a
t
 
g
i
v
e
 
t
h
e
 
b
e
s
t
 
r
e
s
u
l
t
s
 
:
'
,
'
\
n
\
n
'
,
 
(
g
r
i
d
_
s
e
a
r
c
h
.
b
e
s
t
_
p
a
r
a
m
s
_
)
)


#
 
p
r
i
n
t
 
e
s
t
i
m
a
t
o
r
 
t
h
a
t
 
w
a
s
 
c
h
o
s
e
n
 
b
y
 
t
h
e
 
G
r
i
d
S
e
a
r
c
h

p
r
i
n
t
(
'
\
n
\
n
E
s
t
i
m
a
t
o
r
 
t
h
a
t
 
w
a
s
 
c
h
o
s
e
n
 
b
y
 
t
h
e
 
s
e
a
r
c
h
 
:
'
,
'
\
n
\
n
'
,
 
(
g
r
i
d
_
s
e
a
r
c
h
.
b
e
s
t
_
e
s
t
i
m
a
t
o
r
_
)
)
```

<pre>
G
r
i
d
S
e
a
r
c
h
 
C
V
 
b
e
s
t
 
s
c
o
r
e
 
:
 
0
.
8
4
8
3



P
a
r
a
m
e
t
e
r
s
 
t
h
a
t
 
g
i
v
e
 
t
h
e
 
b
e
s
t
 
r
e
s
u
l
t
s
 
:
 


 
{
'
p
e
n
a
l
t
y
'
:
 
'
l
1
'
}



E
s
t
i
m
a
t
o
r
 
t
h
a
t
 
w
a
s
 
c
h
o
s
e
n
 
b
y
 
t
h
e
 
s
e
a
r
c
h
 
:
 


 
L
o
g
i
s
t
i
c
R
e
g
r
e
s
s
i
o
n
(
C
=
1
.
0
,
 
c
l
a
s
s
_
w
e
i
g
h
t
=
N
o
n
e
,
 
d
u
a
l
=
F
a
l
s
e
,
 
f
i
t
_
i
n
t
e
r
c
e
p
t
=
T
r
u
e
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
n
t
e
r
c
e
p
t
_
s
c
a
l
i
n
g
=
1
,
 
l
1
_
r
a
t
i
o
=
N
o
n
e
,
 
m
a
x
_
i
t
e
r
=
1
0
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
u
l
t
i
_
c
l
a
s
s
=
'
w
a
r
n
'
,
 
n
_
j
o
b
s
=
N
o
n
e
,
 
p
e
n
a
l
t
y
=
'
l
1
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
r
a
n
d
o
m
_
s
t
a
t
e
=
0
,
 
s
o
l
v
e
r
=
'
l
i
b
l
i
n
e
a
r
'
,
 
t
o
l
=
0
.
0
0
0
1
,
 
v
e
r
b
o
s
e
=
0
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
w
a
r
m
_
s
t
a
r
t
=
F
a
l
s
e
)

</pre>

```python
#
 
c
a
l
c
u
l
a
t
e
 
G
r
i
d
S
e
a
r
c
h
 
C
V
 
s
c
o
r
e
 
o
n
 
t
e
s
t
 
s
e
t


p
r
i
n
t
(
'
G
r
i
d
S
e
a
r
c
h
 
C
V
 
s
c
o
r
e
 
o
n
 
t
e
s
t
 
s
e
t
:
 
{
0
:
0
.
4
f
}
'
.
f
o
r
m
a
t
(
g
r
i
d
_
s
e
a
r
c
h
.
s
c
o
r
e
(
X
_
t
e
s
t
,
 
y
_
t
e
s
t
)
)
)
```

<pre>
G
r
i
d
S
e
a
r
c
h
 
C
V
 
s
c
o
r
e
 
o
n
 
t
e
s
t
 
s
e
t
:
 
0
.
8
4
8
8

</pre>
#
#
#
 
C
o
m
m
e
n
t
s






-
 
우
리
 
원
래
 
모
델
의
 
테
스
트
 
정
확
도
는
 
0
.
8
4
8
4
이
고
,
 
G
r
i
d
S
e
a
r
c
h
 
C
V
 
정
확
도
는
 
0
.
8
5
0
7
입
니
다
.




-
 
우
리
는
 
이
 
특
정
 
모
델
에
서
 
G
r
i
d
S
e
a
r
c
h
 
C
V
가
 
성
능
을
 
향
상
시
켰
다
는
 
것
을
 
알
 
수
 
있
습
니
다
.


#
 
*
*
2
1
.
 
결
과
와
 
결
론
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
2
1
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)


1
.
 
로
지
스
틱
 
회
귀
 
모
델
의
 
정
확
도
 
점
수
는
 
0
.
8
5
0
1
입
니
다
.
 
따
라
서
,
 
이
 
모
델
은
 
내
일
 
오
스
트
레
일
리
아
에
서
 
비
가
 
올
지
 
여
부
를
 
예
측
하
는
 
데
 
매
우
 
잘
 
작
동
합
니
다
.




2
.
 
일
부
 
관
측
치
는
 
내
일
 
비
가
 
올
 
것
으
로
 
예
측
하
고
 
있
으
며
,
 
대
부
분
의
 
관
측
치
는
 
내
일
 
비
가
 
오
지
 
않
을
 
것
으
로
 
예
측
하
고
 
있
습
니
다
.




3
.
 
모
델
은
 
과
적
합
의
 
징
후
가
 
없
습
니
다
.




4
.
 
C
 
값
을
 
증
가
시
키
면
 
테
스
트
 
세
트
 
정
확
도
와
 
약
간
 
증
가
한
 
훈
련
 
세
트
 
정
확
도
가
 
높
아
집
니
다
.
 
따
라
서
 
더
 
복
잡
한
 
모
델
이
 
더
 
나
은
 
성
능
을
 
발
휘
할
 
것
으
로
 
결
론
 
짓
을
 
수
 
있
습
니
다
.




5
.
 
임
계
값
을
 
높
이
면
 
정
확
도
가
 
증
가
합
니
다
.




6
.
 
모
델
의
 
R
O
C
 
A
U
C
는
 
1
에
 
가
까
워
집
니
다
.
 
따
라
서
,
 
분
류
기
가
 
내
일
 
비
가
 
올
지
 
여
부
를
 
예
측
하
는
 
데
 
매
우
 
잘
 
작
동
한
다
는
 
결
론
을
 
내
릴
 
수
 
있
습
니
다
.




7
.
 
원
래
 
모
델
의
 
정
확
도
 
점
수
는
 
0
.
8
5
0
1
이
고
,
 
R
F
E
C
V
 
이
후
의
 
정
확
도
 
점
수
는
 
0
.
8
5
0
0
입
니
다
.
 
따
라
서
,
 
변
수
의
 
수
를
 
줄
이
면
서
 
거
의
 
유
사
한
 
정
확
도
를
 
얻
을
 
수
 
있
습
니
다
.




8
.
 
원
래
 
모
델
에
서
 
F
P
는
 
1
1
7
5
이
고
,
 
F
P
1
은
 
1
1
7
4
입
니
다
.
 
따
라
서
 
거
의
 
동
일
한
 
수
의
 
거
짓
 
양
성
을
 
얻
을
 
수
 
있
습
니
다
.
 
또
한
,
 
F
N
은
 
3
0
8
7
이
고
,
 
F
N
1
은
 
3
0
9
1
입
니
다
.
 
따
라
서
,
 
약
간
 
더
 
높
은
 
거
짓
 
음
성
을
 
얻
을
 
수
 
있
습
니
다
.


 


9
.
 
우
리
 
원
래
 
모
델
의
 
점
수
는
 
0
.
8
4
7
6
입
니
다
.
 
평
균
 
교
차
 
검
증
 
점
수
는
 
0
.
8
4
7
4
입
니
다
.
 
따
라
서
,
 
교
차
 
검
증
은
 
성
능
 
향
상
을
 
가
져
오
지
 
않
는
 
것
으
로
 
결
론
 
짓
을
 
수
 
있
습
니
다
.




1
0
.
 
우
리
 
원
래
 
모
델
의
 
테
스
트
 
정
확
도
는
 
0
.
8
5
0
1
이
고
,
 
G
r
i
d
S
e
a
r
c
h
 
C
V
 
정
확
도
는
 
0
.
8
5
0
7
입
니
다
.
 
이
 
특
정
 
모
델
에
서
 
G
r
i
d
S
e
a
r
c
h
 
C
V
가
 
성
능
을
 
개
선
시
켰
다
는
 
것
을
 
알
 
수
 
있
습
니
다
.




#
 
*
*
2
2
.
 
참
조
*
*
 
<
a
 
c
l
a
s
s
=
"
a
n
c
h
o
r
"
 
i
d
=
"
2
2
"
>
<
/
a
>






[
T
a
b
l
e
 
o
f
 
C
o
n
t
e
n
t
s
]
(
#
0
.
1
)








T
h
e
 
w
o
r
k
 
d
o
n
e
 
i
n
 
t
h
i
s
 
p
r
o
j
e
c
t
 
i
s
 
i
n
s
p
i
r
e
d
 
f
r
o
m
 
f
o
l
l
o
w
i
n
g
 
b
o
o
k
s
 
a
n
d
 
w
e
b
s
i
t
e
s
:
-






1
.
 
H
a
n
d
s
 
o
n
 
M
a
c
h
i
n
e
 
L
e
a
r
n
i
n
g
 
w
i
t
h
 
S
c
i
k
i
t
-
L
e
a
r
n
 
a
n
d
 
T
e
n
s
o
r
f
l
o
w
 
b
y
 
A
u
r
e
́
l
i
e
́
n
 
G
e
́
r
o
n




2
.
 
I
n
t
r
o
d
u
c
t
i
o
n
 
t
o
 
M
a
c
h
i
n
e
 
L
e
a
r
n
i
n
g
 
w
i
t
h
 
P
y
t
h
o
n
 
b
y
 
A
n
d
r
e
a
s
 
C
.
 
M
u
̈
l
l
e
r
 
a
n
d
 
S
a
r
a
h
 
G
u
i
d
o




3
.
 
U
d
e
m
y
 
c
o
u
r
s
e
 
–
 
M
a
c
h
i
n
e
 
L
e
a
r
n
i
n
g
 
–
 
A
 
Z
 
b
y
 
K
i
r
i
l
l
 
E
r
e
m
e
n
k
o
 
a
n
d
 
H
a
d
e
l
i
n
 
d
e
 
P
o
n
t
e
v
e
s




4
.
 
U
d
e
m
y
 
c
o
u
r
s
e
 
–
 
F
e
a
t
u
r
e
 
E
n
g
i
n
e
e
r
i
n
g
 
f
o
r
 
M
a
c
h
i
n
e
 
L
e
a
r
n
i
n
g
 
b
y
 
S
o
l
e
d
a
d
 
G
a
l
l
i




5
.
 
U
d
e
m
y
 
c
o
u
r
s
e
 
–
 
F
e
a
t
u
r
e
 
S
e
l
e
c
t
i
o
n
 
f
o
r
 
M
a
c
h
i
n
e
 
L
e
a
r
n
i
n
g
 
b
y
 
S
o
l
e
d
a
d
 
G
a
l
l
i




6
.
 
h
t
t
p
s
:
/
/
e
n
.
w
i
k
i
p
e
d
i
a
.
o
r
g
/
w
i
k
i
/
L
o
g
i
s
t
i
c
_
r
e
g
r
e
s
s
i
o
n




7
.
 
h
t
t
p
s
:
/
/
m
l
-
c
h
e
a
t
s
h
e
e
t
.
r
e
a
d
t
h
e
d
o
c
s
.
i
o
/
e
n
/
l
a
t
e
s
t
/
l
o
g
i
s
t
i
c
_
r
e
g
r
e
s
s
i
o
n
.
h
t
m
l




8
.
 
h
t
t
p
s
:
/
/
e
n
.
w
i
k
i
p
e
d
i
a
.
o
r
g
/
w
i
k
i
/
S
i
g
m
o
i
d
_
f
u
n
c
t
i
o
n




9
.
 
h
t
t
p
s
:
/
/
w
w
w
.
s
t
a
t
i
s
t
i
c
s
s
o
l
u
t
i
o
n
s
.
c
o
m
/
a
s
s
u
m
p
t
i
o
n
s
-
o
f
-
l
o
g
i
s
t
i
c
-
r
e
g
r
e
s
s
i
o
n
/




1
0
.
 
h
t
t
p
s
:
/
/
w
w
w
.
k
a
g
g
l
e
.
c
o
m
/
m
n
a
s
s
r
i
b
/
t
i
t
a
n
i
c
-
l
o
g
i
s
t
i
c
-
r
e
g
r
e
s
s
i
o
n
-
w
i
t
h
-
p
y
t
h
o
n




1
1
.
 
h
t
t
p
s
:
/
/
w
w
w
.
k
a
g
g
l
e
.
c
o
m
/
n
e
i
s
h
a
/
h
e
a
r
t
-
d
i
s
e
a
s
e
-
p
r
e
d
i
c
t
i
o
n
-
u
s
i
n
g
-
l
o
g
i
s
t
i
c
-
r
e
g
r
e
s
s
i
o
n




1
2
.
 
h
t
t
p
s
:
/
/
w
w
w
.
r
i
t
c
h
i
e
n
g
.
c
o
m
/
m
a
c
h
i
n
e
-
l
e
a
r
n
i
n
g
-
e
v
a
l
u
a
t
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
-
m
o
d
e
l
/




S
o
,
 
n
o
w
 
w
e
 
w
i
l
l
 
c
o
m
e
 
t
o
 
t
h
e
 
e
n
d
 
o
f
 
t
h
i
s
 
k
e
r
n
e
l
.




I
 
h
o
p
e
 
y
o
u
 
f
i
n
d
 
t
h
i
s
 
k
e
r
n
e
l
 
u
s
e
f
u
l
 
a
n
d
 
e
n
j
o
y
a
b
l
e
.




Y
o
u
r
 
c
o
m
m
e
n
t
s
 
a
n
d
 
f
e
e
d
b
a
c
k
 
a
r
e
 
m
o
s
t
 
w
e
l
c
o
m
e
.




T
h
a
n
k
 
y
o
u




[
G
o
 
t
o
 
T
o
p
]
(
#
0
)

