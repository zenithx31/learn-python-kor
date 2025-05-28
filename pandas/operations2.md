# 판다스의 객체 내 연산

📚 객체 내 연산

판다스(Pandas)에서는 데이터프레임(DataFrame) 객체를 다룰 때 여러 연산을 간단히 할 수 있습니다.

---

## 데이터프레임 예시 생성

```python
import pandas as pd

data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
```

출력:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

---

## 📚 반올림 (round)

round() 메서드를 사용하면 숫자를 반올림할 수 있습니다.

- decimals=0 (기본값): 일의 자리까지 반올림

```python
print(df_example.round(0))
```

출력:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

- decimals>0 (양수): 소수 n번째 자리까지 반올림

```python
print(df_example.round(1))
```

출력:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

- decimals<0 (음수): 10의 n승 자리까지 반올림

```python
print(df_example.round(-1))
```

출력:

```
      col1  col2  col3
row1     0     0     0
row2     0     0    10
row3    10    10    10
```

---

## 📚 합계 (sum)

sum()을 사용하여 열 또는 행의 합계를 구할 수 있습니다.

- 열 방향 합계 (axis=0)

```python
print(df_example.sum(axis=0))
```

출력:

```
col1    12
col2    15
col3    18
```

- 행 방향 합계 (axis=1)

```python
print(df_example.sum(axis=1))
```

출력:

```
row1     6
row2    15
row3    24
```

---

## 📚 곱 (prod)

prod()는 열 또는 행의 곱을 구할 수 있습니다.

- 열 방향 곱 (axis=0)

```python
print(df_example.prod(axis=0))
```

출력:

```
col1     28
col2     80
col3    162
```

- 행 방향 곱 (axis=1)

```python
print(df_example.prod(axis=1))
```

출력:

```
row1      6
row2    120
row3    504
```

---

## 📚 절대값 (abs)

abs()를 사용하면 음수를 양수로 바꿀 수 있습니다.

```python
import pandas as pd

data = [[1, -2, 3], [-4, 5, -6], [7, -8, 9]]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
```

출력:

```
      col1  col2  col3
row1     1    -2     3
row2    -4     5    -6
row3     7    -8     9
```

절대값 계산:

```python
print(df_example.abs())
```

출력:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

---

## 📚 전치 (transpose)

transpose()는 데이터프레임의 행과 열을 뒤집습니다.

단축형으로는 `.T`를 사용할 수 있습니다.

```python
import pandas as pd

data = [[1, 2, 'A'], [4, 5, 'B'], [7, 8, 'C']]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
```

출력:

```
      col1  col2 col3
row1     1     2    A
row2     4     5    B
row3     7     8    C
```

전치:

```python
print(df_example.transpose())
```

출력:

```
      row1  row2  row3
col1     1     4     7
col2     2     5     8
col3     A     B     C
```

---

## 📚 순위 (rank)

rank()를 사용하면 데이터의 순위를 계산할 수 있습니다.

순위를 계산하는 방법에는 여러 가지가 있습니다.

```python
import pandas as pd

data = [[5], [1], [3], [5], [0.1], [30]]
row = ['A', 'B', 'C', 'D', 'E', 'F']
df_example = pd.DataFrame(data=data, index=row, columns=['Value'])
print(df_example)
```

출력:

```
   Value
A    5.0
B    1.0
C    3.0
D    5.0
E    0.1
F   30.0
```

순위 계산 (다양한 방법):

```python
df_example['average'] = df_example['Value'].rank(method='average')
df_example['min'] = df_example['Value'].rank(method='min')
df_example['max'] = df_example['Value'].rank(method='max')
df_example['first'] = df_example['Value'].rank(method='first')
df_example['dense'] = df_example['Value'].rank(method='dense')

print(df_example)
```

출력:

```
   Value  average  min  max  first  dense
A    5.0      4.5  4.0  5.0    4.0    4.0
B    1.0      2.0  2.0  2.0    2.0    2.0
C    3.0      3.0  3.0  3.0    3.0    3.0
D    5.0      4.5  4.0  5.0    5.0    4.0
E    0.1      1.0  1.0  1.0    1.0    1.0
F   30.0      6.0  6.0  6.0    6.0    5.0
```

