# Streaming

## Что это?
- Постепенная выдача токенов по мере генерации (Server-Sent Events).
- Позволяет отображать ответ **в реальном времени** (эффект печатающего текста).

## Как включить?
- В запросе установить: `"stream": true`.

## Формат событий
- Данные приходят в виде `data: {"choices":[{"delta":{"content":"..."}}]}`
- Завершающее сообщение: `data: [DONE]`

## Пример (Python)
```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[...],
    stream=True
)
for chunk in response:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")