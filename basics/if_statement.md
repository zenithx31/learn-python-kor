# 파이썬의 제어문 - if문

📚 **if문의 기초**

파이썬의 if문은 특정 조건을 만족할 때만 코드를 실행하는 기능을 합니다.  
프로그램이 다양한 상황에 맞게 동작하도록 만드는 중요한 문법입니다.

📚 **if문의 기본 구조**

```python
if 조건문:
    수행할 문장 1
    수행할 문장 2
else:
    수행할 문장 A
    수행할 문장 B
```

- if 뒤에는 조건문을 작성하고 반드시 콜론(:)을 붙여야 합니다.  
- 들여쓰기(탭 또는 공백 4칸)를 맞춰야 합니다.  
- else는 if 조건이 거짓(False)일 때 실행됩니다.

**예제**

```python
age = 18

if age >= 18:
    print("성인입니다.")
else:
    print("미성년자입니다.")
```

`age >= 18`이 True이므로 `"성인입니다."`가 출력됩니다.

📚 **if-elif-else 구조**

조건이 여러 개일 때는 `elif` (else if)를 사용할 수 있습니다.

```python
if 조건문 1:
    수행할 문장 1
    수행할 문장 2
elif 조건문 2:
    수행할 문장 A
    수행할 문장 B
else:
    수행할 문장 ㄱ
    수행할 문장 ㄴ
```

- `elif`는 위 조건이 거짓일 때 실행됩니다.  
- `else`는 모든 조건이 거짓일 때 실행됩니다.

**예제**

```python
score = 85

if score >= 90:
    print("A 학점")
elif score >= 80:
    print("B 학점")
else:
    print("C 학점")
```

`score = 85`이므로 `"B 학점"`이 출력됩니다.

📚 **비교 연산자**

if문에서 자주 사용하는 비교 연산자는 다음과 같습니다.

- `x < y` → x가 y보다 작다  
- `x > y` → x가 y보다 크다  
- `x == y` → x와 y가 같다  
- `x != y` → x와 y가 같지 않다  
- `x >= y` → x가 y보다 크거나 같다  
- `x <= y` → x가 y보다 작거나 같다  

**예제**

```python
x = 1
y = 2

print(x < y)   # True
print(x == y)  # False
print(x >= y)  # False
print(x != y)  # True
```

비교 연산의 결과는 항상 `True` 또는 `False`로 반환됩니다.

📚 **논리 연산자 (and, or, not)**

조건을 여러 개 조합할 때 논리 연산자를 사용합니다.

- `x and y` → x와 y 둘 다 참이어야 참  
- `x or y` → x와 y 둘 중 하나라도 참이면 참  
- `not x` → x가 참이면 거짓, 거짓이면 참  

**예제**

```python
x = 10
y = 20

print(x > 5 and y > 15)  # True (둘 다 참)
print(x > 5 or y < 15)   # True (하나만 참이어도 참)
print(not (x > 5))       # False (반대로 변환)
```

- `and`는 모두 참이어야 `True`  
- `or`는 하나라도 참이면 `True`  
- `not`은 참과 거짓을 반대로

📚 **in, not in 연산자**

리스트, 튜플, 문자열에서 특정 값이 존재하는지 확인할 때 사용합니다.

- `x in 리스트/튜플/문자열` → x가 포함되어 있으면 `True`  
- `x not in 리스트/튜플/문자열` → x가 포함되어 있지 않으면 `True`  

**예제**

```python
fruits = ["apple", "banana", "cherry"]

print("banana" in fruits)    # True (banana가 리스트 안에 있음)
print("grape" not in fruits) # True (grape가 리스트 안에 없음)
```

- `"banana" in fruits` → `"banana"`가 리스트에 포함되어 있으므로 `True`  
- `"grape" not in fruits` → `"grape"`가 리스트에 없으므로 `True`

📚 **pass 문**

조건문에서 아무 동작도 하지 않고 넘어가고 싶을 때 `pass`를 사용합니다.

```python
if True:
    pass  # 아무것도 실행하지 않음
else:
    print("실행되지 않음")
```

`pass`는 구문 오류를 방지하는 용도로 사용됩니다.
