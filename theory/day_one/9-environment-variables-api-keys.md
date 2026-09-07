# Environment Variables / API Keys

## Зачем?
- Безопасное хранение ключей вне кода.
- Упрощение деплоя (один .env файл).

## .env файл

OPENAI_API_KEY=sk-...
OPENAI_ORG_ID=org-...

## Загрузка в Python
```bash
pip install python-dotenv
```

```bash
from dotenv import load_dotenv
import os
load_dotenv()
api_key = os.getenv("OPENAI_API_KEY")
```

## Альтернативы

- Переменные окружения ОС (set/export).
- Секреты в CI/CD (GitHub Secrets, GitLab CI/CD).
- Vault-решения (HashiCorp Vault, AWS Secrets Manager).

## Важно!

- Никогда не заливайте ключи в Git.
- Добавьте .env в .gitignore.
- Используйте разные ключи для dev/prod.
- Регулярно ротируйте ключи через панель OpenAI.

