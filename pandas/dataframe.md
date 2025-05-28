# 판다스의 데이터프레임(DataFrame)

## 📚 판다스(Pandas)란?

판다스(Pandas)는 데이터 분석과 처리를 위한 파이썬 라이브러리입니다.  
엑셀과 비슷한 **데이터프레임(DataFrame)** 구조를 활용하여 데이터를 쉽게 다룰 수 있습니다.

---

## 📚 데이터프레임(DataFrame) 생성

우선, 간단한 데이터프레임을 생성해 보겠습니다.

~~~python
import pandas as pd  

# 예제 데이터 생성  
data = [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], 
        [11, 12], [13, 14], [15, 16], [17, 18], [19, 20]]  

col = ['col1', 'col2']  # 열 이름  
row = ['row1', 'row2', 'row3', 'row4', 'row5', 
       'row6', 'row7', 'row8', 'row9', 'row10']  # 행 이름  

df = pd.DataFrame(data=data, index=row, columns=col)  
print(df)
~~~

출력:

```
       col1  col2  
row1      1     2  
row2      3     4  
row3      5     6  
row4      7     8  
row5      9    10  
row6     11    12  
row7     13    14  
row8     15    16  
row9     17    18  
row10    19    20  
```

---

## 📚 데이터프레임 출력 방법

### 1. 상위 데이터 출력 (`head()`)

~~~python
print(df.head())      # 기본: 상위 5개 행 출력
print(df.head(8))     # 상위 8개 행 출력
~~~

### 2. 하위 데이터 출력 (`tail()`)

~~~python
print(df.tail())      # 기본: 하위 5개 행 출력
print(df.tail(8))     # 하위 8개 행 출력
~~~

### 3. 랜덤 데이터 출력 (`sample()`)

~~~python
print(df.sample())      # 랜덤 1개 행
print(df.sample(5))     # 랜덤 5개 행
~~~

---

## 📚 데이터프레임 기본 정보 확인

### 1. 인덱스 확인 (`index`)

~~~python
print(df.index)
~~~

출력:

```
Index(['row1', 'row2', 'row3', 'row4', 'row5', 
       'row6', 'row7', 'row8', 'row9', 'row10'], 
      dtype='object')
```

### 2. 데이터 타입 확인 (`dtypes`)

~~~python
print(df.dtypes)
~~~

출력:

```
col1    int64  
col2    int64  
dtype: object
```

### 3. 데이터 크기 확인 (`shape`)

~~~python
print(df.shape)
~~~

출력:

```
(10, 2)  # 10개의 행, 2개의 열
```

### 4. 행렬 값 확인 (`values`)

~~~python
print(df.values)
~~~

출력:

```
[[ 1  2]  
 [ 3  4]  
 [ 5  6]  
 [ 7  8]  
 [ 9 10]  
 [11 12]  
 [13 14]  
 [15 16]  
 [17 18]  
 [19 20]]
```

### 5. 전체 정보 확인 (`info()`)

~~~python
print(df.info())
~~~

출력:

```
<class 'pandas.core.frame.DataFrame'>  
Index: 10 entries, row1 to row10  
Data columns (total 2 columns):  
 #   Column  Non-Null Count  Dtype  
---  ------  --------------  -----  
 0   col1    10 non-null     int64  
 1   col2    10 non-null     int64  
dtypes: int64(2)  
memory usage: 240.0+ bytes  
```

---

## 📚 결측값(Null) 확인

결측값이란 데이터가 존재하지 않는 상태를 의미합니다.  
판다스에서는 `isnull()` 메서드를 통해 확인할 수 있습니다.

### 1. 결측값 여부 확인 (`isnull()`)

~~~python
print(df.isnull())
~~~

출력:

```
       col1   col2  
row1  False  False  
row2  False  False  
row3  False  False  
row4  False  False  
row5  False  False  
row6  False  False  
row7  False  False  
row8  False  False  
row9  False  False  
row10 False  False
```

→ 모든 값이 `False`이므로 결측값 없음.

### 2. 결측값 개수 확인 (`isnull().sum()`)

~~~python
print(df.isnull().sum())
~~~

출력:

```
col1    0  
col2    0  
dtype: int64
```

→ 결측값이 0이므로 데이터는 모두 존재합니다.

---
