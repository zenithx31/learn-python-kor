# 판다스의 조건부 로직, 연산자, 정렬

---

## 📚 데이터프레임 조건부 로직

판다스에서는 특정 조건을 만족하는 데이터를 필터링할 수 있습니다.

---

### 1. 조건을 만족하는 행 선택

```python
df['열이름'] == '조건'
```

**예제:**

```python
import pandas as pd  

data = {'number': [100, 50, 200, 100, 300],  
        'value': [10, 20, 30, 40, 50]}  
df_sample = pd.DataFrame(data)  

filtered_df = df_sample[df_sample['number'] == 100]
print(filtered_df)
```

**출력:**

```
   number  value  
0    100     10  
3    100     40  
```

---

### 2. 조건을 만족하는 상위 N개 행 선택

```python
df[df['열이름'] == '조건'].head(N)
```

**예제:**

```python
print(df_sample[df_sample['number'] == 100].head(1))
```

**출력:**

```
   number  value  
0    100     10  
```

---

### 3. 결측값(null) 확인 및 필터링

#### 1) 결측값 여부 확인

```python
df['열이름'].isnull()
```

**예제:**

```python
df_sample['number'].isnull()
```

**출력:**

```
0    False  
1    False  
2    False  
3    False  
4    False  
```

#### 2) 결측값이 있는 행만 출력

```python
df[df['열이름'].isnull()]
```

---

## 📚 데이터프레임 연산자 (AND, OR, NOT)

여러 개의 조건을 조합하여 데이터를 필터링할 수 있습니다.

---

### 1. NOT (~): 조건 제외

```python
df[~(조건)]
```

**예제:**

```python
print(df_sample[~(df_sample['number'] == 100)])
```

**출력:**

```
   number  value  
1     50     20  
2    200     30  
4    300     50  
```

---

### 2. AND (&): 모든 조건 만족

```python
df[(조건1) & (조건2)]
```

**예제:**

```python
print(df_sample[(df_sample['number'] == 100) & (df_sample['value'] == 10)])
```

**출력:**

```
   number  value  
0    100     10  
```

---

### 3. OR (|): 하나라도 만족

```python
df[(조건1) | (조건2)]
```

**예제:**

```python
print(df_sample[(df_sample['number'] == 100) | (df_sample['value'] == 50)])
```

**출력:**

```
   number  value  
0    100     10  
3    100     40  
4    300     50  
```

---

## 📚 데이터프레임 정렬

---

### 1. 단일 열 기준 정렬

```python
df.sort_values('열이름')  # 오름차순  
df.sort_values('열이름', ascending=False)  # 내림차순  
```

**예제:**

```python
print(df_sample.sort_values('number'))
```

**출력:**

```
   number  value  
1     50     20  
0    100     10  
3    100     40  
2    200     30  
4    300     50  
```

```python
print(df_sample.sort_values('number', ascending=False))
```

**출력:**

```
   number  value  
4    300     50  
2    200     30  
0    100     10  
3    100     40  
1     50     20  
```

---

### 2. 여러 개의 열 기준 정렬

```python
df.sort_values(['열이름1', '열이름2'])
```

**예제:**

```python
print(df_sample.sort_values(['number', 'value']))
```

**출력:**

```
   number  value  
1     50     20  
0    100     10  
3    100     40  
2    200     30  
4    300     50  
```
