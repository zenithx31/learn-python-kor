# FinanceDataReader 라이브러리로 금융 데이터 가져오기

---

## 📚 FinanceDataReader란?

금융 데이터를 쉽게 수집하고 분석할 수 있도록 도와주는 파이썬 라이브러리입니다.  
이 라이브러리를 사용하면 한국 주식 가격, 미국 주식 가격, 암호화폐 가격, 상품 선물 가격, 다양한 지수, 환율, 그리고 종목 리스트 등 다양한 금융 데이터를 가져올 수 있습니다.

---

## 📚 설치 방법

FinanceDataReader를 설치하려면 먼저 Python과 pip 모듈이 설치되어 있어야 합니다.  
그 후 아래 명령어로 라이브러리를 설치할 수 있습니다.

~~~bash
$ pip install -U finance-datareader
~~~

---

## 📚 종목 리스트 가져오기

### 1. 한국 거래소에 상장된 종목 리스트 모두 가져오기

~~~python
import FinanceDataReader as fdr

df_sample = fdr.StockListing('KRX')
print(df_sample)
~~~

~~~
       Code        ISU_CD      Name  ...           Marcap      Stocks MarketId
0     005930  KR7005930003      삼성전자  ...  417884778500000  5969782550      STK
1     373220  KR7373220003  LG에너지솔루션  ...  100503000000000   234000000      STK
2     000660  KR7000660001    SK하이닉스  ...   92747501301000   728002365      STK
3     207940  KR7207940008  삼성바이오로직스  ...   51957020000000    71174000      STK
4     005935  KR7005931001     삼성전자우  ...   46575387220000   822886700      STK
...      ...           ...       ...  ...              ...         ...      ...
2764  245450  KR7245450002    씨앤에스링크  ...       2678032200     1579960      KNX
2765  308700  KR7308700004       테크엔  ...       2560000000     4000000      KNX
2766  288490  KR7288490006     나라소프트  ...       2466219285    43267005      KNX
2767  217320  KR7217320001       썬테크  ...       2420250000     1050000      KNX
2768  322190  KR7322190000        베른  ...       1017472458     8925197      KNX

[2769 rows x 17 columns]
~~~

---

### 2. 특정 종목을 필터링해서 가져오기 (ex. 삼성전자)

~~~python
import FinanceDataReader as fdr

# 삼성전자, 2023년부터 현재까지
df_sample1 = fdr.DataReader(symbol='005930', start='2023') 

# 삼성전자, 2023년 1월 1일부터 2023년 10월 31일까지
df_sample2 = fdr.DataReader(symbol='005930', start='20230101', end='20231031') 

# 삼성전자, 상장일부터 현재까지
df_sample3 = fdr.DataReader(symbol='005930') 

print(df_sample1.head())
print(df_sample2.head())
print(df_sample3.head())
~~~

~~~
           Open   High    Low  Close    Volume    Change
Date                                                      
2023-01-02  55500  56100  55200  55500  10031448  0.003617
2023-01-03  55400  56000  54500  55400  13547030 -0.001802
2023-01-04  55700  58000  55600  57800  20188071  0.043321
2023-01-05  58200  58800  57600  58200  15682826  0.006920
2023-01-06  58300  59400  57900  59000  17334989  0.013746

           Open   High    Low  Close    Volume    Change
Date                                                      
2023-01-02  55500  56100  55200  55500  10031448  0.003617
2023-01-03  55400  56000  54500  55400  13547030 -0.001802
2023-01-04  55700  58000  55600  57800  20188071  0.043321
2023-01-05  58200  58800  57600  58200  15682826  0.006920
2023-01-06  58300  59400  57900  59000  17334989  0.013746

       Open  High   Low  Close   Volume    Change
Date                                                  
1999-07-23  3400  3400  3000   3120  1180685       NaN
1999-07-26  3120  3260  3060   3170  1212761  0.016026
1999-07-27  3229  3399  3200   3370   910512  0.063091
1999-07-28  3409  3750  3390   3560  1952152  0.056380
1999-07-29  3699  3960  3570   3940  1661889  0.106742
~~~

---

### 3. 미국 S&P 500 지수에 등록된 종목 리스트 가져오기

~~~python
import FinanceDataReader as fdr

df_sp500 = fdr.StockListing('S&P500')
print(df_sp500)
~~~

~~~
     Code         ISU_CD              Name             ...        Marcap          Stocks  MarketId
0    0001Z     US0378331005      Apple Inc.       ...   2535210000000   16500000000   NYSE
1    0002Y     US5949181045      Microsoft Corp.  ...   2171400000000   7460000000    NASDAQ
2    0003X     US0231351067      Amazon.com Inc.   ...   1576450000000   5120000000    NASDAQ
3    0004W     US0378331005      Tesla, Inc.       ...   1162100000000   1540000000    NASDAQ
4    0005V     US68389X1054      Meta Platforms    ...    920000000000   2435000000    NASDAQ
...   ...           ...                   ...    ...         ...              ...   ...

[500 rows x 17 columns]
~~~

---

### 4. 종목 가격을 그래프로 확인하기 (ex. 삼성전자)

~~~python
import FinanceDataReader as fdr
import matplotlib.pyplot as plt

df_sample = fdr.DataReader(symbol='005930') # 삼성전자

df_sample['Close'].plot()
plt.show()
~~~

---

## 📚 전체 종목 데이터 - StockListing() 함수

아래 종목 데이터는 StockListing() 함수를 사용합니다.

- 한국 거래소 : ‘KRX’, ‘KOSPI’, ‘KOSDAQ’, ‘KONEX’, ‘KRX-DELISTING’, ‘KRX-ADMINSTRATIVE’
- 미국 거래소 : ‘NASDAQ’, ‘NYSE’, ‘AMEX’, ‘S&P500’
- 글로벌 거래소 : ‘SSE’, ‘SZSE’, ‘HKEX’, ‘TSE’, ‘HOSE’ 등

---

## 📚 가격 데이터 - DataReader() 함수

아래 가격 데이터는 DataReader() 함수를 사용합니다.

- 국내 주식 : ‘005930’, ‘000660’, ‘068270’ 등
- 해외 주식 : ‘AAPL’, ‘AMZN’, ‘GOOG’ 등
- 국내 지수 : ‘KS11’, ‘KQ11’, ‘KS200’
- 미국 지수 : ‘DJI’, ‘IXIC’, ‘US500’, ‘RUT’, ‘VIX’
- 환율 (지원 : ’KRW’, ‘EUR’, ‘CNY’, ‘JPY’, ‘CHF’) : ‘USD/KRW’, ‘USD/EUR’, ‘CNY/KRW’, ‘EUR/CNY’ 등
- 암호 화폐 (지원 : ‘BTC’, ‘ETH’, ‘USDT’, ‘BNB’, ‘USDC’, ‘XRP’, ‘BUSD’, ‘ADA’, ‘SOL’, ‘DOGE’) : ‘BTC/USD’, ‘BTC/KRW’, ‘ETH/USD’, ‘ETH/KRW’ 등
- 상품 선물 : ‘CL=F’, ‘BZ=F’, ‘NG=F’, ‘GC=F’, ‘SI=F’, ‘HG=F’
- 그외 : ‘ETF/KR’, ‘US5YT’ 등

---

※ FinanceDataReader 라이브러리의 더 자세한 정보는 아래 링크에서 확인할 수 있습니다.

- [FinanceDataReader 사용자 안내서](https://financedata.github.io/posts/finance-data-reader-users-guide.html)
- [FinanceDataReader API 정보](https://github.com/FinanceData/FinanceDataReader/wiki/)
