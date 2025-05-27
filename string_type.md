# 파이썬의 문자열 자료형

## 📚 문자열 자료형

---

### 1. 문자열 정의하기

문자열은 작은 따옴표 `'`나 큰 따옴표 `"`로 둘러싸여 있습니다.  
3개의 따옴표(`'''` 또는 `"""`)를 사용하면 여러 줄에 걸친 문자열을 정의할 수 있습니다.

```python
# 큰 따옴표로 문자열
a = "Hello World!"

# 작은 따옴표로 문자열
b = 'Hello World!'

# 여러 줄 문자열 (큰 따옴표 3개)
c = """Hello
World!"""

# 여러 줄 문자열 (작은 따옴표 3개)
d = '''Hello
World!'''
```

---

### 2. 문자열에 백슬래시(`\`) 사용하기

문자열 안에서 따옴표를 포함시키고 싶을 때, 백슬래시(`\`)를 사용해 특수 문자를 이스케이프 할 수 있습니다.

```python
# 작은 따옴표 안에 큰 따옴표 사용
a = "Life is too short. You need 'Python'."

# 큰 따옴표 안에 작은 따옴표 사용
b = 'Life is too short. You need "Python".'

# 작은 따옴표를 그대로 사용하고 싶을 때
c = 'Life is too short. You need \'Python\'.'
```

---

### 3. 이스케이프 코드

이스케이프 코드를 사용하면, 문자열 안에서 특별한 기능을 수행할 수 있습니다.

- `\n`: 줄 바꿈  
- `\t`: 탭 간격  
- `\\`: 백슬래시 `\`를 그대로 사용  
- `\'`: 작은 따옴표를 그대로 사용  
- `\"`: 큰 따옴표를 그대로 사용  

```python
# 줄 바꿈
a = "Life is too short.\nYou need Python."
print(a)

# 탭 간격
b = "Life is too short.\tYou need Python."
print(b)

# 백슬래시
c = "This is a backslash: \\"
print(c)

# 작은 따옴표와 큰 따옴표
d = "He said, \"Python is great!\""
print(d)
```

---

### 4. 문자열 연산

문자열은 다양한 연산을 통해 결합하거나 반복할 수 있습니다.

#### 1) 문자열 덧셈 (`+`)

```python
a = "Life is"
b = " too short."
print(a + b)  # "Life is too short."
```

#### 2) 문자열 곱셈 (`*`)

```python
a = "Life"
print(a * 2)  # "LifeLife"
```

#### 3) 문자열 길이 구하기 (`len()`)

```python
a = "Life is too short."
print(len(a))  # 17
```

---

### 5. 문자열 인덱싱과 슬라이싱

#### 1) 문자열 인덱싱

문자열에서 특정 위치의 문자를 가져옵니다.  
인덱스는 0부터 시작하며, 음수 인덱스를 사용하면 뒤에서부터 문자를 읽을 수 있습니다.

```python
a = "Life is too short"
print(a[3])   # 'e'
print(a[-1])  # 't'
```

#### 2) 문자열 슬라이싱

문자열의 일부분을 추출할 때 슬라이싱을 사용합니다.

```python
a = "Life is too short"
print(a[0:4])  # "Life"
```

---

### 6. 문자열 포매팅

문자열 안에 변수를 삽입하려면 포매팅을 사용할 수 있습니다.

#### 1) `%` 포매팅

```python
a = 5
b = "five"
print("I eat %d apples." % a)
print("I eat %s apples." % b)
```

#### 2) `.format()` 함수

```python
a = 5
b = "five"
print("I ate {0} apples for {1} days.".format(a, b))
```

#### 3) f-문자열 (Python 3.6 이상)

```python
a = 'John'
b = 20
print(f"My name is {a}. I am {b} years old.")
```

---

### 7. 문자열 내장 함수

#### 1) 문자 개수 세기 (`count`)

```python
a = "Happy"
print(a.count("p"))  # 2
```

#### 2) 문자 위치 찾기 (`find`, `index`)

```python
a = "Life is too short"
print(a.find('e'))  # 3
```

#### 3) 문자열 변경 (`replace`)

```python
a = "Life is too short"
print(a.replace("short", "long"))  # Life is too long
```

#### 4) 문자열 나누기 (`split`)

```python
a = "Life is too short"
print(a.split())  # ['Life', 'is', 'too', 'short']

b = "a/b/c/d"
print(b.split('/'))  # ['a', 'b', 'c', 'd']
```

