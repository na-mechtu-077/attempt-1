# Python SDK

## Установка
```bash
pip install openai
```

## Инициализация клиента
```bash
from openai import OpenAI
client = OpenAI(api_key="your-key")  # или через переменную окружения
```

## Базовый запрос (синхронный)
```bash
completion = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Привет!"}]
)
print(completion.choices[0].message.content)
```

## Асинхронный вариант
```bash
from openai import AsyncOpenAI
aclient = AsyncOpenAI()
```

## Полезные методы

- create() — отправка запроса.
- with_streaming_response — для стриминга с контролем.
- Обработка ошибок через try/except openai.APIError.

## Советы

- Держите SDK актуальным (pip install --upgrade openai).
- Используйте typing для лучшей поддержки IDE.
