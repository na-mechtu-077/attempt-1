# API Request / Response

## Структура запроса (Request)
- **Endpoint**: `https://api.openai.com/v1/chat/completions`
- **Метод**: `POST`
- **Заголовки**:
  - `Authorization: Bearer <API_KEY>`
  - `Content-Type: application/json`
- **Тело (JSON)**:
  - `model`: идентификатор модели (например, `gpt-4o`)
  - `messages`: массив объектов с ролями и контентом
  - `temperature`, `max_tokens` и др. (опционально)

## Структура ответа (Response)
- Успех (200 OK):
  ```json
  {
    "id": "chatcmpl-...",
    "object": "chat.completion",
    "created": 1234567890,
    "model": "gpt-4o",
    "choices": [
      {
        "index": 0,
        "message": {
          "role": "assistant",
          "content": "Ответ модели"
        },
        "finish_reason": "stop"
      }
    ],
    "usage": {
      "prompt_tokens": 10,
      "completion_tokens": 20,
      "total_tokens": 30
    }
  }

- Ключевые поля: choices[0].message.content — сам ответ, usage — статистика по токенам.


