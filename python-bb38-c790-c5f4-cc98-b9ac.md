# Python 문자열 처리



파이썬에서 문자열 출력을 테스트 해봅시다. 앞서 작성한 코드와 매우 유사한 느낌\(?\)이 있지만, 연습이라 생각하고 해봅시다.

새로운 파이썬 파일 `string_test.py`를 만들어 봅시다.



```py
# -*- coding:utf:8 -*-

mac1 =  "맥"
mac2 =  "도"
mac3 =  "날"
mac4 =  "드"

ham1 =  "빅"
ham2 =  "맥"

msg1 =  "마"
msg2 =  "시"
msg3 =  "쪙"

print mac1+mac2+mac3+mac4,
print ham1+ham2,
print msg1+msg2+msg3
```

마지막 줄에서 2,3번째 줄에 ham2 그리고 mac4 다음에 쉼표가 보입니다. 우선 그대로 출력해보고 쉼표를 지워보면 어떻게 변하는지 직접 해봅시다.



---

# Python 문자열 포매터

매번 앞서 작성한 것 처럼, `print` 문에 + 기호로 붙여써야할까요? 조금 더 쉽고 간단한 방법이 있습니다. 

다음 예제를 통해서 Python 에선 문자열 포매터에 대해서 알아보도록 하겠습니다.



새로운 파이썬 파일 `string_formatter.py`를 만들어 봅시다.

```py
# -*- coding:utf:8 -*-

formatter1 = "%s %s %s %s"
formatter2 = "%s%s %s%s"

print formatter1 %(1,2,3,4)
print formatter2 %(1,2,3,4)

print formatter1 %("난","너를","지울","수 있을까")
print formatter2 %("그저"," 한 순간에","우린 ","남이 될 수 있을까")

print formatter1 %("볼빨간","사춘기","오춘기","육춘기")
print formatter2 %("아이유","아인","슈타인","기스타")

print formatter1 %(formatter1,formatter1,formatter1,formatter1)
print formatter2 %(formatter2,formatter2,formatter2,formatter2)
```

오타 및 띄어쓰기에 주의해주세요! 조금 복잡하지만 쉽게 이해할 수 있습니다. 포매터는 언제 사용 해야할까요? 날짜, 통화, 요일 등 이미 지정된 포맷이 존재합니다. 이럴 때 마다 매번 뒤에 붙여주는 형식이 아니라, 포맷을 만들어서 재사용할 수 있게 해주면 편하겠죠?

---

만약 한글 때문에 오류가 발생하였다면, 다음 과정을 통해서 해결할 수 있습니다.

1. 파이썬 파일 최 상단에 `# -*- coding:utf:8 -*-`  코드를 추가하세요.
2. 그래도 해결이 안된다면, 한글로 쓴 문자 앞에 소문자 u 를 추가해봅시다.

```py
print formatter1 %(u"난",u"너를",u"지울",u"수 있을까")
print formatter2 %(u"그저",u" 한 순간에",u"우린 ",u"남이 될 수 있을까")
```

아마도 파이썬 2.7 버전에서 이런 오류가 종종 나오곤 합니다. \(물론 1번으로 해결이 대부분 될겁니다.\)







