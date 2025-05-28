# 데이터프레임 행과 열 생략 없이 전체 출력하기

## 📚 데이터프레임 생략 없이 전체 출력

~~~
pd.set_option('display.max_rows', None)
pd.set_option('display.max_columns', None)
~~~

---

## 📚 예시

~~~
import pandas as pd
import FinanceDataReader as fdr

df_sample = fdr.StockListing('KRX')
print(df_sample)
~~~

![](images/df1.png)

FinanceDataReader를 활용해 한국 거래소에 상장된 종목 코드를 가져왔습니다.

양이 많다보니 ···으로 생략이 된 행과 열이 보입니다.

---

위의 코드를 입력해 데이터프레임 행렬의 생략 없이 모두 출력해보겠습니다.

~~~
import pandas as pd
import FinanceDataReader as fdr

df_sample = fdr.StockListing('KRX')
pd.set_option('display.max_rows', None)
pd.set_option('display.max_columns', None)

print(df_sample)
~~~

![](images/df2.png)

아웃풋을 한 화면에 담을 수 없어 일부만 크롭해 보여드리고 있지만,

실제 실행 후 살펴보면 데이터프레임 행렬의 생략없이 모두 출력되었음을 확인할 수 있습니다.
