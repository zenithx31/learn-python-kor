# 파이썬의 제어문 - while문

## 📚 while문 기초

반복문은 같은 동작을 여러 번 실행할 때 사용합니다.  
그중 `while`문은 특정 조건이 참(`True`)인 동안 계속 실행됩니다.

---

## 📚 while문의 기본 구조

```python
while 조건문:
    수행할 문장 1
    수행할 문장 2
    수행할 문장 3
    ...
```

- 조건문이 `True`인 동안 `while`문 안의 코드가 반복 실행됩니다.
- 조건이 `False`가 되면 `while`문이 종료됩니다.

**예제**

```python
count = 0  # 변수 초기화

while count < 5:  # count가 5보다 작을 동안 실행
    print("반복 중입니다:", count)
    count += 1  # count 값을 1씩 증가
```

**결과**

```
반복 중입니다: 0  
반복 중입니다: 1  
반복 중입니다: 2  
반복 중입니다: 3  
반복 중입니다: 4  
```

5번째 반복이 끝난 후 `count`가 5가 되어 조건이 `False`가 되므로 종료됩니다.

---

## 📚 while문 강제 종료 (break문)

`break` 문을 사용하면 `while`문을 강제로 종료할 수 있습니다.

**예제**

```python
num = 1

while num <= 10:
    print(num)
    
    if num == 5:  # num이 5가 되면 반복문 종료
        break
    
    num += 1
```

**결과**

```
1  
2  
3  
4  
5
```

`5`에서 `break`가 실행되어 반복문이 종료됩니다.

---

## 📚 while문 처음으로 돌아가기 (continue문)

`continue` 문을 사용하면 현재 반복을 건너뛰고, 다음 반복을 실행합니다.

**예제**

```python
num = 0

while num < 5:
    num += 1
    
    if num == 3:  # num이 3일 때는 실행하지 않고 넘어감
        continue

    print(num)
```

**결과**

```
1  
2  
4  
5
```

`num == 3`일 때 `continue`가 실행되어 `print(num)`이 생략됩니다.

---

## 📚 while문 무한 루프 방지

`while`문을 사용할 때는 **종료 조건을 명확히 설정**해야 합니다.  
조건이 항상 참(`True`)이라면 무한 루프(끝없이 반복)가 발생할 수 있습니다.

**잘못된 예제 (무한 루프 발생)**

```python
num = 0

while num < 5:
    print("무한 루프!")
```

- 실행하면 `num` 값이 변하지 않기 때문에 무한히 반복됩니다.

**올바른 예제**

```python
num = 0

while num < 5:
    print("반복 중:", num)
    num += 1  # 조건을 False로 만들기 위한 변화
```
