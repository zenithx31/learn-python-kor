# 판다스의 객체 간 연산

## 📚 객체 간 연산

판다스(Pandas)에서는 DataFrame 또는 Series와 같은 객체 간에 다양한 연산을 쉽게 수행할 수 있습니다.

---

### 데이터 프레임 예시 생성

먼저 간단한 데이터프레임을 만들어봅시다.

~~~python
import pandas as pd

# 데이터 정의
data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']

# DataFrame 생성
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
~~~

출력:

~~~
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
~~~

---

## 📚 덧셈 (add, radd)

### 1. 숫자와의 덧셈

DataFrame에 숫자를 더하면 모든 값에 그 숫자가 더해집니다.

~~~python
result1 = df_example.add(1)
print(result1)
~~~

출력:

~~~
      col1  col2  col3
row1     2     3     4
row2     5     6     7
row3     8     9    10
~~~

add()와 + 연산자는 동일한 결과를 얻을 수 있습니다.

~~~python
result2 = df_example + 1
print(result2)
~~~

출력:

~~~
      col1  col2  col3
row1     2     3     4
row2     5     6     7
row3     8     9    10
~~~

---

### 2. 다른 DataFrame과의 덧셈

다음은 두 개의 DataFrame 객체를 더하는 예시입니다.

NaN 값은 기본적으로 연산에서 무시됩니다.

~~~python
data_add = [[3], [4], [5]]
df_add = pd.DataFrame(data=data_add, index=['row1', 'row2', 'row3'], columns=['col1'])

result3 = df_example.add(df_add)
print(result3)
~~~

출력:

~~~
      col1  col2  col3
row1     4   NaN   NaN
row2     8   NaN   NaN
row3    12   NaN   NaN
~~~

---

### 3. NaN 값 처리하기

fill_value 옵션을 사용하여 NaN을 다른 값으로 채울 수 있습니다.

~~~python
result4 = df_example.add(df_add, fill_value=1)  # NaN일 경우 1을 채워넣음
print(result4)
~~~

출력:

~~~
      col1  col2  col3
row1     4   3.0   4.0
row2     8   6.0   7.0
row3    12   9.0  10.0
~~~

---

## 📚 뺄셈 (sub, rsub)

### 1. 숫자와의 뺄셈

~~~python
result1 = df_example.sub(1)
print(result1)
~~~

출력:

~~~
      col1  col2  col3
row1     0     1     2
row2     3     4     5
row3     6     7     8
~~~

sub()와 - 연산자는 동일하게 작동합니다.

~~~python
result2 = df_example - 1
print(result2)
~~~

출력:

~~~
      col1  col2  col3
row1     0     1     2
row2     3     4     5
row3     6     7     8
~~~

---

### 2. 다른 DataFrame과의 뺄셈

~~~python
result3 = df_example.sub(df_add)
print(result3)
~~~

출력:

~~~
      col1  col2  col3
row1    -2   NaN   NaN
row2     0   NaN   NaN
row3     2   NaN   NaN
~~~

---

### 3. NaN 값 처리하기

~~~python
result4 = df_example.sub(df_add, fill_value=1)
print(result4)
~~~

출력:

~~~
      col1  col2  col3
row1    -2   1.0   2.0
row2     0   4.0   5.0
row3     2   7.0   8.0
~~~

---

## 📚 곱셈 (mul, rmul)

### 1. 숫자와의 곱셈

~~~python
result1 = df_example.mul(2)
print(result1)
~~~

출력:

~~~
      col1  col2  col3
row1     2     4     6
row2     8    10    12
row3    14    16    18
~~~

---

### 2. 다른 DataFrame과의 곱셈

~~~python
result3 = df_example.mul(df_add)
print(result3)
~~~

출력:

~~~
      col1  col2  col3
row1     3   NaN   NaN
row2    16   NaN   NaN
row3    35   NaN   NaN
~~~

---

### 3. NaN 값 처리하기

~~~python
result4 = df_example.mul(df_add, fill_value=1)
print(result4)
~~~

출력:

~~~
      col1  col2  col3
row1     3   2.0   3.0
row2    16   5.0   6.0
row3    35   8.0   9.0
~~~

---

## 📚 나눗셈 (div, rdiv)

### 1. 숫자와의 나눗셈

~~~python
result1 = df_example.div(2)
print(result1)
~~~

출력:

~~~
      col1  col2  col3
row1   0.5   1.0   1.5
row2   2.0   2.5   3.0
row3   3.5   4.0   4.5
~~~

---

### 2. 다른 DataFrame과의 나눗셈

~~~python
result3 = df_example.div(df_add)
print(result3)
~~~

출력:

~~~
      col1  col2  col3
row1  0.333333   NaN   NaN
row2  1.000000   NaN   NaN
row3  1.400000   NaN   NaN
~~~

---

### 3. NaN 값 처리하기

~~~python
result4 = df_example.div(df_add, fill_value=1)
print(result4)
~~~

출력:

~~~
      col1  col2  col3
row1  0.333333   2.0   3.0
row2  1.000000   5.0   6.0
row3  1.400000   8.0   9.0
~~~

---

## 📚 나머지 (mod, rmod)

### 1. 숫자와의 나머지

~~~python
result1 = df_example.mod(2)
print(result1)
~~~

출력:

~~~
      col1  col2  col3
row1     1     0     1
row2     0     1     0
row3     1     0     1
~~~

---

## 📚 거듭제곱 (pow, rpow)

### 1. 숫자와의 거듭제곱

~~~python
result1 = df_example.pow(2)
print(result1)
~~~

출력:

~~~
      col1  col2  col3
row1     1     4     9
row2    16    25    36
row3    49    64    81
~~~

---

### 2. 다른 DataFrame과의 거듭제곱

~~~python
result3 = df_example.pow(df_add)
print(result3)
~~~

출력:

~~~
      col1  col2  col3
row1      1   NaN   NaN
row2    256   NaN   NaN
row3  16807   NaN   NaN
~~~

---

## 📚 행렬곱 (dot)

행렬곱은 dot() 메서드를 사용하여 두 DataFrame 간의 행렬곱을 수행할 수 있습니다.

~~~python
# 데이터프레임 예시 생성
data1 = [[1, 2], [3, 4]]
data2 = [[5, 6], [7, 8]]
df1 = pd.DataFrame(data=data1)
df2 = pd.DataFrame(data=data2)

result = df1.dot(df2)
print(result)
~~~

출력:

~~~
    0   1
0  19  22
1  43  50
~~~
