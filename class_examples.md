# 클래스(Class) 작성 방법과 활용 예시

📚 클래스의 기본 구조

클래스는 `class` 키워드를 사용해 정의하며, 클래스 내에는 속성(데이터)과 메소드(기능)를 정의할 수 있습니다.

예시

~~~python
class 클래스이름:
    # 클래스 생성자 정의
    def __init__(self, 인자1, 인자2):
        self.속성1 = 인자1
        self.속성2 = 인자2

    # 메소드 구현
    def 메소드1(self):
        # 코드 구현
        pass

    def 메소드2(self):
        # 코드 구현
        pass

# 메인 코드 영역
# 인스턴스 생성
c1 = 클래스이름(c1의 인자1, c1의 인자2)
c2 = 클래스이름(c2의 인자1, c2의 인자2)

# 메소드 사용하여 인스턴스 활용
c1.메소드1()
c2.메소드1()

c1.메소드2()
c2.메소드2()
~~~

**설명**

- `class 클래스이름`  
  클래스를 정의할 때 사용합니다.

- `__init__(self, 인자1, 인자2)`  
  클래스 생성자입니다. 객체가 생성될 때 자동으로 호출되며, 주로 객체의 초기 속성을 설정하는 역할을 합니다.

- `self.속성 = 값`  
  객체의 속성을 설정하는 부분입니다. `self`는 해당 객체를 참조하는 변수입니다.

- 메소드 정의  
  클래스 내부에 기능을 구현할 때 사용하는 함수들이며, 객체가 수행할 동작을 정의합니다.

- 인스턴스 생성  
  클래스를 사용하여 객체를 생성할 때는 `클래스이름(인자1, 인자2)` 형식으로 인스턴스를 만듭니다.

- 메소드 호출  
  객체가 가진 메소드를 `c1.메소드()`와 같은 형식으로 호출할 수 있습니다.

---

📚 클래스의 활용 예시 (아이들의 키)

예시

~~~python
class Child:
    def __init__(self, Child_Name, Child_Height):
        self.name = Child_Name
        self.height = Child_Height

    def getName(self):
        return self.name

    def getHeight(self):
        return self.height

    def growHeight(self, add):
        before = self.height
        self.height += add
        print("성장했습니다. {}->{}".format(before, self.height))

# 인스턴스 생성
c1 = Child('Tom', 150)
c2 = Child('Jerry', 100)

# 현재 키 출력
print("현재 {}의 키는 {}cm입니다.".format(c1.getName(), c1.getHeight()))
print("현재 {}의 키는 {}cm입니다.".format(c2.getName(), c2.getHeight()))

# 성장하기
c1.growHeight(10)
c2.growHeight(30)

# 성장 후 키 출력
print("현재 {}의 키는 {}cm입니다.".format(c1.getName(), c1.getHeight()))
print("현재 {}의 키는 {}cm입니다.".format(c2.getName(), c2.getHeight()))
~~~

**설명**

- `Child` 클래스  
  아이의 이름과 키를 속성으로 가지는 클래스를 정의합니다.

- `__init__` 생성자  
  아이의 이름과 키를 인자로 받아 `self.name`, `self.height`에 저장합니다.

- `getName` 메소드  
  아이의 이름을 반환합니다.

- `getHeight` 메소드  
  아이의 키를 반환합니다.

- `growHeight` 메소드  
  키를 성장시키는 기능입니다. 인자로 받은 `add`만큼 키를 증가시키고, 전후를 출력합니다.

**결과**

```
현재 Tom의 키는 150cm입니다.
현재 Jerry의 키는 100cm입니다.
성장했습니다. 150->160
성장했습니다. 100->130
현재 Tom의 키는 160cm입니다.
현재 Jerry의 키는 130cm입니다.
```

`c1`과 `c2`는 `Child` 클래스의 인스턴스로, 각각 Tom과 Jerry라는 이름을 가진 아이들을 나타냅니다. 아이들의 키를 출력하고, `growHeight()` 메소드로 성장한 결과를 확인할 수 있습니다.
