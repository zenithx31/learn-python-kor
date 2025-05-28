# Telethon 라이브러리로 텔레그램 채팅방 스크래핑 하기

## 📚 Telethon이란?

Telethon은 Python으로 작성된 Telegram API 클라이언트 라이브러리입니다.  
텔레그램 서버와 직접 통신하여 메시지 전송, 수신, 채팅방 관리 등 다양한 작업을 자동화할 수 있도록 도와줍니다.  
비동기 방식을 지원하여 대용량 데이터 처리에도 효율적입니다.

---

## 📚 Telegram API와 Hash 발급

텔레그램 API와 Hash는 텔레그램 계정이 있어야 발급이 가능하며, 계정이 있다면 아래 링크에서 발급 받을 수 있습니다.

https://my.telegram.org/auth?to=apps

---

## 📚 Telegram 채팅방 스크래핑 예시

Telethon을 설치하려면 먼저 Python과 pip 모듈이 설치되어 있어야 합니다.

그 후 아래 명령어로 라이브러리를 설치할 수 있습니다.

~~~bash
pip install pandas
pip install telethon
~~~

~~~python
import pandas as pd
from telethon import TelegramClient

# 발급 받은 id와 hash, 그리고 스크래핑 할 채팅방의 링크를 넣어줍니다.
name = 'test'
api_id = '<api_id>'
api_hash = '<api_hash>'
chat = '<chat_link>'

data = []

# 텔레그램 서버와 연결
async def some_function():
    async with TelegramClient(name, api_id, api_hash) as client:
        async for message in client.iter_messages(chat):
            data.append([message.sender_id, message.text])

df = pd.DataFrame(data, columns=['SENDER', 'MESSAGE'])
df.to_csv('test.csv', encoding='utf-8')
~~~

위의 예제 코드를 사용해 지정한 텔레그램 채팅방의 메시지를 비동기 방식으로 하나씩 가져올 수 있습니다.

가져온 메시지는 데이터프레임 형태로 저장되며 to_csv() 함수를 사용해 csv 파일로 내보도록 만들었습니다.
