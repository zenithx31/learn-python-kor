# 파이썬의 입력과 출력 - 함수

## 📚 함수를 사용하는 이유

- 반복적으로 사용되는 부분이 있을 때 이를 한 덩어리로 묶어둔 후 효율적으로 재사용하기 위해  
- 프로그램의 흐름을 일목요연하게 보기 위해

---

## 📚 함수의 기본 구조

```python
def 함수명(매개변수):
    수행할 문장 1
    수행할 문장 2
    ...
```

- `def` 키워드를 사용하여 함수를 정의합니다.  
- 매개변수는 함수가 실행될 때 전달받는 값입니다.  
- `return`을 사용하면 값을 반환할 수 있습니다.

### 예제: 두 숫자를 더하는 함수

```python
def add(a, b):
    return a + b
```

---

## 📚 매개변수와 인수

- 매개변수 (Parameter): 함수에서 입력값을 받는 변수  
- 인수 (Argument): 함수를 호출할 때 전달하는 실제 값

### 예제

```python
def add(a, b):  # a, b는 매개변수
    return a + b

print(add(3, 4))  # 3, 4는 인수
```

**결과**

```
7
```

---

## 📚 입력값이 있는 함수 (일반적인 함수)

함수에 입력값(인수)을 전달하면, 결과를 계산하여 반환합니다.

```python
def add(a, b):
    result = a + b
    return result

a = add(3, 4)
print(a)
```

**결과**

```
7
```

---

## 📚 입력값이 없는 함수

함수에 입력값을 주지 않으면, 수행할 문장이 없거나 `None`을 반환할 수 있습니다.

```python
def say_hello():
    print("안녕하세요!")

say_hello()
```

**결과**

```
안녕하세요!
```

---

## 📚 입력값의 개수를 모를 때 (*args)

매개변수 앞에 `*`을 붙이면 여러 개의 인수를 튜플 형태로 받을 수 있습니다.

```python
def add(*args):
    result = 0
    for i in args:
        result += i
    return result

print(add(1, 2, 3))         # 6
print(add(1, 2, 3, 4, 5))   # 15
```

---

## 📚 키워드 매개변수 (**kwargs)

매개변수 앞에 `**`을 붙이면 딕셔너리 형태로 값을 받을 수 있습니다.

```python
def print_kwargs(**kwargs):
    print(kwargs)

print_kwargs(a=1)  
# {'a': 1}

print_kwargs(name="Alice", age=25)  
# {'name': 'Alice', 'age': 25}
```

---

## 📚 매개변수 지정하여 호출하기

함수를 호출할 때 매개변수를 지정하면 순서와 상관없이 사용할 수 있습니다.

```python
def add(a, b):
    return a + b

result = add(b=2, a=1)
print(result)  # 3
```

---

## 📚 global 명령어 (전역 변수 사용하기)

함수 내부에서 함수 밖의 변수를 변경하려면 `global` 키워드를 사용해야 합니다.

```python
a = 1

def test():
    global a  # 함수 밖의 변수 a를 사용
    a += 1

test()
print(a)  # 2
```

- `global` 사용은 권장되지 않으며, 가능하면 함수의 반환값을 활용하는 것이 좋습니다.

---

## 📚 lambda (간단한 함수 만들기)

`lambda`는 한 줄짜리 함수를 만들 때 사용됩니다.

```python
add = lambda a, b: a + b

print(add(3, 4))  # 7
```

일반 함수로 작성하면 이렇게 됩니다.

```python
def add(a, b):
    return a + b
```

- `lambda`는 짧고 간단한 연산을 수행할 때 유용합니다.
