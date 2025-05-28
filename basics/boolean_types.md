# 파이썬의 불 자료형

## 📚 불 자료형 기초

파이썬에서 불(Boolean) 자료형은 참(True)과 거짓(False)을 나타내는 자료형입니다.  
주로 조건문에서 참과 거짓을 판별할 때 사용됩니다.

---

## 📚 불 자료형의 값

불 자료형에는 두 가지 값이 있습니다.

```python
print(True)   # True
print(False)  # False
```

True와 False는 반드시 첫 글자를 대문자로 작성해야 합니다.  
소문자로 true 또는 false를 쓰면 오류가 발생합니다.

---

## 📚 불 자료형의 비교 연산

불 자료형은 비교 연산의 결과로도 자주 사용됩니다.

```python
print(3 > 1)   # True
print(3 < 1)   # False
print(3 == 3)  # True
print(3 != 3)  # False
print(5 >= 3)  # True
print(2 <= 1)  # False
```

비교 연산의 결과는 항상 True 또는 False로 반환됩니다.

---

## 📚 불 자료형의 논리 연산

불 자료형은 `and`, `or`, `not` 같은 논리 연산자와 함께 자주 사용됩니다.

```python
print(True and False)  # False
print(True or False)   # True
print(not True)        # False
```

- `and` 연산자는 모든 조건이 참이어야 True를 반환합니다.  
- `or` 연산자는 하나라도 참이면 True를 반환합니다.

---

## 📚 불 자료형의 조건문

불 자료형은 조건문에서 중요한 역할을 합니다.

```python
age = 18

if age >= 18:
    print("성인입니다.")  # 출력: 성인입니다.
else:
    print("미성년자입니다.")
```

위 코드에서 `age >= 18`의 결과는 True이므로, "성인입니다."가 출력됩니다.

---

## 📚 불 자료형과 다른 자료형

파이썬에서는 숫자, 문자열, 리스트 등 다양한 자료형도 참(True) 또는 거짓(False)으로 평가될 수 있습니다.

- 거짓(False)으로 간주되는 값

  - `0` (정수 0, 실수 0.0)  
  - `""` (빈 문자열)  
  - `[]` (빈 리스트)  
  - `{}` (빈 딕셔너리)  
  - `set()` (빈 집합)  
  - `None` (값이 없음)  

```python
print(bool(0))      # False
print(bool(""))     # False
print(bool([]))     # False
print(bool(None))   # False
```

반면, 이외의 값은 모두 True로 평가됩니다.

```python
print(bool(1))          # True
print(bool("hello"))    # True
print(bool([1, 2, 3]))  # True
```
