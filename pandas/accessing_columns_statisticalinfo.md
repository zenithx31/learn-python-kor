# 판다스의 데이터프레임 열 접근 & 수치 정보

---

## 📚 데이터프레임 열 접근

판다스에서 특정 열(column)에 접근하는 방법은 여러 가지가 있습니다.

### 1. 단일 열 접근

```python
df.열이름      # 점(.)을 이용한 접근
df['열이름']   # 대괄호([])를 이용한 접근
```

예제:

```python
import pandas as pd  

# 예제 데이터 생성  
data = {'number1': [10, 20, 30, 40, 50],  
        'number2': [5, 15, 25, 35, 45]}  
df_sample = pd.DataFrame(data)  

# 단일 열 출력
print(df_sample.number1)  
print(df_sample['number1'])  
```

출력:

```
0    10  
1    20  
2    30  
3    40  
4    50  
Name: number1, dtype: int64  
```

---

### 2. 여러 개의 열 접근

```python
df[['열이름1', '열이름2']]
```

예제:

```python
print(df_sample[['number1', 'number2']])
```

출력:

```
   number1  number2  
0       10        5  
1       20       15  
2       30       25  
3       40       35  
4       50       45  
```

> `점(.)` 방식은 단일 열에만 사용 가능  
> 여러 열을 선택할 때는 리스트 형식 `[[]]` 사용

---

## 📚 데이터프레임 수치 정보

판다스를 사용하면 통계 정보를 쉽게 확인할 수 있습니다.

---

### 1. 전체 데이터의 기본 통계 (`describe()`)

```python
df.describe()
```

예제:

```python
print(df_sample.describe())
```

출력:

```
        number1  number2  
count       5.0       5.0  
mean       30.0      25.0  
std        15.8      15.8  
min        10.0       5.0  
25%        20.0      15.0  
50%        30.0      25.0  
75%        40.0      35.0  
max        50.0      45.0  
```

설명:

- `count`: 데이터 개수  
- `mean`: 평균값  
- `std`: 표준편차  
- `min`: 최소값  
- `25%, 50%, 75%`: 분위수 (중앙값 포함)  
- `max`: 최대값

---

### 2. 특정 열의 통계 정보

```python
df['열이름'].describe()
```

예제:

```python
print(df_sample['number1'].describe())
```

출력:

```
count     5.0  
mean     30.0  
std      15.8  
min      10.0  
25%      20.0  
50%      30.0  
75%      40.0  
max      50.0  
```

---

### 3. 개별 수치 정보

```python
df['열이름'].mean()   # 평균  
df['열이름'].max()    # 최대값  
df['열이름'].min()    # 최소값  
df['열이름'].sum()    # 합계  
df['열이름'].count()  # 데이터 개수  
```

예제:

```python
print("평균:", df_sample['number1'].mean())  
print("최대값:", df_sample['number1'].max())  
print("최소값:", df_sample['number1'].min())  
print("합계:", df_sample['number1'].sum())  
print("개수:", df_sample['number1'].count())  
```

출력:

```
평균: 30.0  
최대값: 50  
최소값: 10  
합계: 150  
개수: 5  
```

---
