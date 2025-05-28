# 넘파이 기본 문법과 활용 예시

📚 Numpy란?

Numpy는 Numeric + Python의 약자입니다.  
수치 데이터를 다룰 수 있는 Python 패키지로, 순수 파이썬보다 훨씬 빠르게 대규모 데이터를 처리할 수 있습니다.  
특히 다차원 배열인 `ndarray`를 사용하여 벡터와 행렬을 효율적으로 다룰 수 있습니다.

주로 선형 대수 계산, 과학적 연산, 데이터 분석에 많이 활용됩니다.

---

📚 np.array()

Numpy에서 가장 중요한 데이터 구조인 `ndarray`를 만들 때 사용하는 함수입니다.

### 1) 1차원 배열
~~~python
import numpy as np
vec = np.array([1, 2, 3, 4, 5])
print(vec)
# 출력
# [1 2 3 4 5]
~~~

### 2) 2차원 배열
~~~python
import numpy as np
mat = np.array([[10, 20, 30], [40, 50, 60]])
print(mat)
# 출력
# [[10 20 30]
#  [40 50 60]]
~~~

### 3) 타입 확인
~~~python
print(type(vec))
print(type(mat))
# 출력
# <class 'numpy.ndarray'>
# <class 'numpy.ndarray'>
~~~

### 4) 차원 확인
~~~python
print(vec.ndim)  # 1차원
print(mat.ndim)  # 2차원
# 출력
# 1
# 2
~~~

### 5) 크기 확인
~~~python
print(vec.shape)  # (5,)
print(mat.shape)  # (2, 3)
# 출력
# (5,)
# (2, 3)
~~~

---

📚 ndarray 초기화

Numpy는 배열을 쉽게 초기화할 수 있는 다양한 방법을 제공합니다.

### 1) 0으로 채워진 배열
~~~python
import numpy as np
zero = np.zeros((2, 3))
print(zero)
# 출력
# [[0. 0. 0.]
#  [0. 0. 0.]]
~~~

### 2) 1로 채워진 배열
~~~python
import numpy as np
one = np.ones((2, 3))
print(one)
# 출력
# [[1. 1. 1.]
#  [1. 1. 1.]]
~~~

### 3) 특정 값으로 채워진 배열
~~~python
import numpy as np
same_value = np.full((2, 3), 5)
print(same_value)
# 출력
# [[5 5 5]
#  [5 5 5]]
~~~

### 4) 대각선 1인 단위 행렬
~~~python
import numpy as np
eye = np.eye(5)
print(eye)
# 출력
# [[1. 0. 0. 0. 0.]
#  [0. 1. 0. 0. 0.]
#  [0. 0. 1. 0. 0.]
#  [0. 0. 0. 1. 0.]
#  [0. 0. 0. 0. 1.]]
~~~

### 5) 랜덤 값으로 채워진 배열
~~~python
import numpy as np
random = np.random.random((2, 3))
print(random)
# 출력
# [[0.55580566 0.58351512 0.6544916 ]
#  [0.09908401 0.25436744 0.44398083]]
~~~

---

📚 np.arange()

`np.arange()` 함수는 주어진 범위의 숫자들을 포함하는 배열을 생성합니다.

### 1) 0부터 n-1까지 배열 생성
~~~python
import numpy as np
range_vec = np.arange(10)
print(range_vec)
# 출력
# [0 1 2 3 4 5 6 7 8 9]
~~~

### 2) n씩 증가하는 배열 생성
~~~python
import numpy as np
n = 2
range_step_vec = np.arange(1, 10, n)
print(range_step_vec)
# 출력
# [1 3 5 7 9]
~~~

---

📚 np.reshape()

`np.reshape()` 함수는 배열의 데이터를 그대로 두고, 배열의 모양만 변경할 수 있습니다.

~~~python
import numpy as np
reshape = np.array(np.arange(30))
reshape = reshape.reshape((5, 6))
print(reshape)
~~~

---

📚 Numpy 슬라이싱

Numpy 배열을 슬라이싱하여 원하는 부분을 추출할 수 있습니다.

### 1) 첫 번째 행 추출
~~~python
import numpy as np
mat = np.array([[1, 2, 3], [4, 5, 6]])
slice_mat1 = mat[0, :]
print(slice_mat1)
# 출력
# [1 2 3]
~~~

### 2) 첫 번째 열 추출
~~~python
slice_mat2 = mat[:, 0]
print(slice_mat2)
# 출력
# [1 4]
~~~

---

📚 Numpy 정수 인덱싱

배열의 특정 위치를 지정하여 값을 추출하거나 새로운 배열을 생성할 수 있습니다.

### 1) 특정 위치의 원소 출력
~~~python
import numpy as np
mat = np.array([[1, 2], [3, 4], [5, 6]])
print(mat[1, 0])  # 3
# 출력
# 3
~~~

### 2) 정수 인덱싱을 통한 새로운 배열 생성
~~~python
index_mat = mat[[2, 1], [0, 1]]
print(index_mat)
# 출력
# [5 4]
~~~

---

📚 Numpy 연산

Numpy는 배열 간의 연산을 간단히 처리할 수 있게 해줍니다.

### 1) 덧셈
~~~python
import numpy as np
x = np.array([1, 2, 3])
y = np.array([4, 5, 6])
result1 = x + y
result2 = np.add(x, y)
print(result1)
print(result2)
# 출력
# [5 7 9]
# [5 7 9]
~~~

### 2) 뺄셈
~~~python
result1 = x - y
result2 = np.subtract(x, y)
print(result1)
print(result2)
# 출력
# [-3 -3 -3]
# [-3 -3 -3]
~~~

### 3) 나눗셈
~~~python
result1 = x / y
result2 = np.divide(x, y)
print(result1)
print(result2)
# 출력
# [0.25 0.4  0.5 ]
# [0.25 0.4  0.5 ]
~~~

### 4) 곱셈 (요소별 곱셈)
~~~python
result1 = x * y
print(result1)
# 출력
# [ 4 10 18]
~~~

### 5) 벡터와 행렬 곱셈
~~~python
result2 = np.dot(x, y)
print(result2)
# 출력
# 32
~~~
