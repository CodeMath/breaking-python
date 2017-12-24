# Python 변수란?

앞서 배운 `print` 를 이용해 출력을 해보았습니다. 그리고 사칙연산 등을 이용해 계산을 해보았습니다.

이제 "변수" 라는 것을 배워볼 차례입니다. 일단 사전적 정의로 변수란,

> 컴퓨터 프로그래밍에서 "**변수**"는 아직 알려지지 않거나 어느 정도까지만 알려져 있는 양이나 정보에 대한 상징적인 이름이다. 컴퓨터 소스 코드에서의 변수 이름은 일반적으로 데이터 저장 위치와 그 안의 내용물과 관련되어 있으며 이러한 것들은 프로그램 실행 도중에 변경될 수 있다.
>
> 프로그래밍에서의 변수는 수학에서 말하는 변수의 개념과 완전히 일치하지 않을 수 도 있다. 컴퓨터 변수의 값은 수학에서처럼 등식이나 공식의 필수적인 부분이 아니다. 컴퓨터 환경에서 변수는 반복적인 과정 안에서 이용할 수 있다. 이를테면 한 장소의 값을 할당한 뒤 어느 곳 에서 사용한 다음 새로운 값으로 다시 할당하고 같은 방법으로 다시 사용할 수 있다.    - [위키백과](https://ko.wikipedia.org/wiki/변수_%28컴퓨터_과학%29)

사실 위키백과에서 서술한 설명이 잘 이해가 되지 않을 수 있습니다. 조금 어렵게 느껴지신다면 일단 저렇구나.... 라고 생각하고 넘어간 뒤 실제 코드를 작성하면서 이해해봅시다. 앞서 연습했던 것 처럼 우선 소스코드를 먼저 작성해보겠습니다.

새로운 파이썬 파일 `variable_int.py`를 만들어 봅시다.

```py
# -*- coding: utf-8 -*-

bike = 50
school_bus = 300
student = 500
texi = 250

all_car = school_bus + texi
ride_a_bike = bike
get_texi = student - bike - school_bus
rate_of_getting_bus = school_bus / student

print "학교 시험보러가는 길"
print "자전거는 ", bike, "대 뿐이다."
print "자전거를 무료로 탈 수 있는 인원은 ", ride_a_bike, "명 이다."

print "학교로 가는 버스에 총 ", school_bus, "명만 탈 수 있다."
print "현재 도로 위 자동차에 총 ", all_car , "명만 탈 수 있다."

print "자전거, 버스를 놓친 학생들은 택시에 타야한다."
print "택시를 탈 수 있는 최대 인원이 ", texi, "명이므고 현재 남아있는 학생은 ", get_texi ,"명 이다."
print "모든 학생이 시험장에 잘 도착했는가?", texi > get_texi
```

일단 상확극으로 자격증 시험을 보러 특정 학교에 가야하는 상황입니다. 500명의 학생들이 자격증 시험을 보러 가는데, 무료로 자전거를 타고 갈 수 있고 스쿨버스를 타고 갈 수 있습니다. \(우선적으로 무료로 자전거를 먼저 타고 갔다는 상황입니다.\)

아직 소스코드를 실행하지 말고, 앞에서 했던 작업인 주석을 이용해서 먼저 예상해봅시다. 어떤식으로 출력되어 나올지 생각해봅시다.

---

# 변수를 받고 출력하기

앞서 숫자를 계산해서 출력하는 것을 해보았습니다. 이번에는 숫자 이외의 변수를 더 많이 받아서 출력해보도록 하겠습니다.

이번 장에서는 "포멧팅"에 대해서 배울 예정입니다. 앞서 문자를 만들 때, "" 큰 따옴표를 이용했습니다. 이처럼 큰 따옴표를 이용해서 만드는 것을 문자열이라고 부릅니다. 쉽게 말해 보여지는 텍스트값이라고 생각하면 됩니다.

서두가 너무 길었네요. 코드를 보면서 이야기해봅시다.

새로운 파이썬 파일 `variable_another.py`를 만들어 봅시다.

```py
# -*- coding: utf-8 -*-

my_resume = "이력서"
my_career = "서버 개발자"
my_region = "인천"
my_education = "대졸"
my_blog = "https://codemath.github.io"

th_year = 5
main_language = "python"
sub_language = "swift"

strong_knowledge = "python, django, html, javascript"
knowledge = "swift, docker, css, kotlin, react"


print "이 문서는 제 %s 입니다." %my_resume
print "현재는 %s 에서 거주하고 있습니다." %my_region
print "제 학력사항은 %s 입니다." %my_education

print "저는 %d 년차, %s 입니다." %(th_year, my_career)
print "주 언어는 %s 이고, 부 언어로 %s 를 사용합니다." %(main_language, sub_language)

print "제 기술 스택은 다음과 같습니다."
print "잘 알고 있는 부분은 %s 입니다." %strong_knowlege
print "조금 알고 있는 부분은 %s 입니다." %knowledge

print "블로그는 %s 에서 확인하실 수 있습니다." %my_blog

print "한 줄로 정리하면, %s 에 거주 중인 %d 년차 %s %s 입니다." %(my_region, th_year, main_language, my_career)
```

역시나 바로 실행하지말고 주석을 달아서 예상해봅시다.

### **추가 문제**

1. `my_resume`  변수 이름을 바꿔서 출력해보세요. \(오류가 난다면 고쳐보세요\)

2. 마지막 `print "한 줄로 정리하면, %s 에 거주 중인 %d 년차 %s %s 입니다." %(my_region, th_year, main_language, my_career)` 문에서 `%d`가 아니라 `%s` 로 해서 출력해보세요.





---













