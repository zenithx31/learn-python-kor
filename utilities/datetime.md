# datetime 라이브러리로 날짜와 시간 다루기: 파이썬 데이터 타입 변환

## 📚 datetime이란?

datetime은 파이썬의 표준 라이브러리로, 날짜와 시간을 다루는 데 필요한 다양한 기능을 제공합니다.  
주로 시계열 데이터를 처리하거나 시간 관련 계산을 할 때 유용하게 사용됩니다.

- **time** : 시간을 다루는 클래스  
  시, 분, 초, 마이크로초 등을 포함하여 하루 동안의 특정 시간을 표현할 수 있습니다.

- **date** : 날짜를 다루는 클래스  
  연, 월, 일을 표현하며, 특정 날짜에 대한 연산이나 비교에 사용됩니다.

- **datetime** : 날짜와 시간을 모두 포함하는 클래스  
  연, 월, 일뿐만 아니라 시, 분, 초, 마이크로초도 포함되어 있어, 날짜와 시간을 동시에 처리해야 할 때 사용됩니다.

---

## 📚 데이터 타입 변환하기 (string ↔ datetime)

1. **string을 datetime으로 전환**

~~~python
import datetime

datetime_str = '2023-11-08 16:00:00'
format = '%Y-%m-%d %H:%M:%S'
datetime_dt = datetime.datetime.strptime(datetime_str, format)
print(datetime_dt)
print(type(datetime_dt))
# 출력:
# 2023-11-08 16:00:00
# <class 'datetime.datetime'>
~~~

2. **datetime을 string으로 전환**

~~~python
import datetime

datetime_str = '2023-11-08 16:00:00'
format = '%Y-%m-%d %H:%M:%S'
datetime_dt = datetime.datetime.strptime(datetime_str, format)

datetime_str = datetime_dt.strftime('%Y-%m-%d %H:%M:%S')
print(datetime_str)
print(type(datetime_str))
# 출력:
# 2023-11-08 16:00:00
# <class 'str'>
~~~
