# 파이썬의 딕셔너리 자료형

## 📚 딕셔너리란?

딕셔너리(Dictionary)는 Key(키)와 Value(값)를 한 쌍으로 저장하는 자료형입니다.  
리스트나 튜플처럼 순서(index)가 아니라 Key를 이용해 데이터를 저장하고 조회하는 방식을 사용해요.

```python
# 딕셔너리 생성 예시
a = {'name': 'Alice', 'age': 25, 'city': 'Seoul'}
b = {1: 'one', 2: 'two', 3: 'three'}
c = {'fruits': ['apple', 'banana', 'cherry']}  # Value에 리스트 저장 가능
```

---

## 📚 딕셔너리 요소 추가

새로운 Key-Value 쌍을 추가할 때는 딕셔너리[새로운 Key] = Value 형태로 작성합니다.

```python
a = {1: 'a'}
a[2] = 'b'  # 새로운 요소 추가

print(a)  # {1: 'a', 2: 'b'}
```

---

## 📚 딕셔너리 요소 삭제

딕셔너리에서 특정 Key를 삭제할 때는 `del`을 사용합니다.

```python
a = {1: 'a', 2: 'b'}
del a[1]  # Key 1을 삭제

print(a)  # {2: 'b'}
```

---

## 📚 Key를 이용해 Value 찾기

딕셔너리에서 Key를 이용해 값을 찾을 수 있습니다.

1) 딕셔너리 Key 사용

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a['a'])  # 1
print(a['c'])  # 3
```

이때, 존재하지 않는 Key를 조회하면 오류가 발생합니다.

2) `get()` 사용

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.get('a'))  # 1
print(a.get('c'))  # 3
print(a.get('d'))  # None (Key가 없으면 오류 대신 None 반환)
```

`get()`을 사용하면 Key가 없을 때도 오류가 발생하지 않으므로 안전합니다.

---

## 📚 Key 리스트 생성

딕셔너리의 모든 Key를 가져오려면 `keys()`를 사용합니다.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.keys())  # dict_keys(['a', 'b', 'c'])
```

리스트처럼 사용하려면 `list(a.keys())`로 변환하면 됩니다.

---

## 📚 특정 Key가 존재하는지 확인하기

`in` 연산자를 사용하면 Key가 딕셔너리에 있는지 확인할 수 있습니다.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print('b' in a)  # True
print('d' in a)  # False
```

---

## 📚 Value 리스트 생성

딕셔너리의 모든 Value를 가져오려면 `values()`를 사용합니다.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.values())  # dict_values([1, 2, 3])
```

리스트처럼 사용하려면 `list(a.values())`로 변환하면 됩니다.

---

## 📚 Key - Value 쌍 얻기

Key와 Value를 튜플 쌍 형태로 가져오려면 `items()`를 사용합니다.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.items())  # dict_items([('a', 1), ('b', 2), ('c', 3)])
```

`for` 문과 함께 사용하면 딕셔너리의 Key와 Value를 쉽게 반복할 수 있습니다.

```python
for key, value in a.items():
    print(f'Key: {key}, Value: {value}')
```

# 결과

```
Key: a, Value: 1
Key: b, Value: 2
Key: c, Value: 3
```

---

## 📚 딕셔너리 비우기 (초기화)

딕셔너리의 모든 요소를 삭제하고 비울 때 `clear()`를 사용합니다.

```python
a = {'a': 1, 'b': 2, 'c': 3}

a.clear()
print(a)  # {}
```
