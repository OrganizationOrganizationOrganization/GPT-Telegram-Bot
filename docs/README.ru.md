# GPT-Telegram-Bot: Многофункциональный ИИ-ассистент 🤖💬

[English](../README.md) | [简体中文](./README.zh-cn.md) | [繁體中文](./README.zh-hant.md) | [日本語](./README.ja.md) | [Español](./README.es.md) | [Français](./README.fr.md) | [Русский](./README.ru.md) | [Deutsch](./README.de.md)

GPT-Telegram-Bot — это мощный Telegram-бот, интегрирующий различные модели ИИ, обеспечивающий интеллектуальные беседы, генерацию и анализ изображений.
[![Развернуть с Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/OrganizationOrganizationOrganization/GPT-Telegram-Bot)
## Основные функции 🌟

1. **Поддержка нескольких моделей** 🎭: Любая модель, совместимая с API OpenAI, Google Gemini, Anthropic Claude, Groq и Azure OpenAI
2. **Интеллектуальные беседы** 💬: Взаимодействие на естественном языке с поддержкой контекстной памяти
3. **Генерация изображений** 🎨: Создание изображений на основе текстовых описаний
4. **Анализ изображений** 🔍: Интерпретация и описание загруженных изображений
5. **Многоязычная поддержка** 🌐: Поддержка локализации для нескольких языков
6. **Потоковый ответ** ⚡: Генерация и отображение ответов ИИ в реальном времени
7. **Белый список пользователей** 🔐: Может быть настроен для разрешения доступа только определенным пользователям

## Поддерживаемые модели ИИ 🧠

- Серия OpenAI: Мощные языковые модели 🚀
- Google Gemini: Модель ИИ нового поколения от Google 🧑‍🔬
- Anthropic Claude: Еще один мощный выбор языковой модели 🎭
- Groq: Высокоскоростная модель ИИ для логического вывода ⚡
- Azure OpenAI: Сервис OpenAI, размещенный Microsoft 👔

## Структура проекта 📁

```
GPT-Telegram-Bot/
├── api/                # Конфигурация, связанная с API
│   ├── telegram.js     # Обрабатывает взаимодействия с ботом Telegram
├── src/                # Исходный код
│   ├── api.js          # Обрабатывает взаимодействия с совместимыми с OpenAI API
│   ├── bot.js          # Основная логика бота Telegram
│   ├── config.js       # Файл конфигурации
│   ├── azureOpenAI.js  # Обрабатывает взаимодействия с Azure OpenAI
│   ├── claude.js       # Обрабатывает взаимодействия с Claude
│   ├── generateImage.js# Обрабатывает взаимодействия с DALL·E
│   ├── geminiApi.js    # Обрабатывает взаимодействия с Gemini
│   ├── groqapi.js      # Обрабатывает взаимодействия с Groq
│   ├── uploadhandler.js# Обрабатывает логику загрузки и анализа изображений
│   ├── localization.js # Обрабатывает многоязычную поддержку
│   ├── redis.js        # Функциональность базы данных Upstash Redis
├── locales/            # Файлы многоязычной поддержки
│   ├── en.json         
│   ├── zh-cn.json      
│   ├── zh-hant.json    
│   └── ja.json         
│   └── es.json         
│   └── fr.json         
│   └── ru.json         
│   └── de.json         
├── docs/               # Многоязычные файлы README
│   ├── README.zh-cn.md 
│   ├── README.zh-hant.md
│   ├── README.ja.md    
│   ├── README.es.md    
│   ├── README.fr.md    
│   ├── README.ru.md    
│   └── README.de.md    
├── public/             # Веб-страница Vercel после развертывания
│   └── index.html      # Входной файл веб-страницы
├── package.json        # Зависимости проекта
├── vercel.json         # Файл конфигурации Vercel
└── README.md           # Файл описания проекта
```

## Быстрый старт 🚀

### Предварительные требования

- Аккаунт [Vercel](https://vercel.com/)
- Аккаунт Telegram и токен бота
- База данных [Upstash](https://upstash.com/) Пожалуйста, выберите базу данных Redis и включите функцию [Eviction](https://upstash.com/docs/redis/features/eviction)
- API-ключ хотя бы для одного ИИ-сервиса

### Шаги развертывания

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/snakeying/GPT-Telegram-Bot.git
   cd GPT-Telegram-Bot
   ```

2. Установите зависимости:
   ```bash
   npm install
   ```

3. Настройте переменные окружения:
   Создайте файл `.env` и заполните необходимую информацию конфигурации (см. конфигурацию переменных окружения ниже).

4. Разверните на Vercel:
   - Сделайте форк этого репозитория
   - Измените согласно инструкциям в нижней части readme
   - Нажмите кнопку "Развернуть с Vercel"
   - Подключите свой репозиторий GitHub
   - Настройте переменные окружения
   - Завершите развертывание

5. Настройте Telegram Webhook:
   После развертывания используйте следующий URL для настройки Webhook:
   ```
   https://api.telegram.org/bot<ВАШ_ТОКЕН_БОТА>/setWebhook?url=<ВАШ_ДОМЕН_VERCEL>/api/telegram
   ```

## Конфигурация переменных окружения 🔧

Перед развертыванием и запуском GPT-Telegram-Bot вам нужно настроить следующие переменные окружения. Создайте файл `.env` в корневой директории проекта и настройте следующие переменные:

| Имя переменной | Описание | Значение по умолчанию |
|----------------|----------|------------------------|
| `OPENAI_API_KEY` | API-ключ OpenAI | - |
| `OPENAI_BASE_URL` | Базовый URL API OpenAI | https://api.openai.com/v1 |
| `OPENAI_MODELS` | Модели OpenAI для использования (разделенные запятыми) | - |
| `DEFAULT_MODEL` | Модель для использования по умолчанию | Первая модель в OPENAI_MODELS |
| `AZURE_OPENAI_API_KEY` | API-ключ Azure OpenAI | - |
| `AZURE_OPENAI_ENDPOINT` | Конечная точка Azure OpenAI | - |
| `AZURE_OPENAI_MODELS` | Модели Azure OpenAI для использования (разделенные запятыми) | - |
| `TELEGRAM_BOT_TOKEN` | Токен Telegram-бота | - |
| `WHITELISTED_USERS` | Разрешенные ID пользователей (разделенные запятыми) | - |
| `DALL_E_MODEL` | Модель DALL-E для использования | dall-e-3 |
| `UPSTASH_REDIS_REST_URL` | REST URL Upstash Redis | - |
| `UPSTASH_REST_TOKEN` | REST токен Upstash Redis | - |
| `SYSTEM_INIT_MESSAGE` | Системное инициализационное сообщение | You are a helpful assistant. |
| `SYSTEM_INIT_MESSAGE_ROLE` | Роль системного сообщения | system |
| `GEMINI_API_KEY` | API-ключ Google Gemini | - |
| `GOOGLE_MODELS` | Модели Google для использования (разделенные запятыми) | - |
| `GEMINI_ENDPOINT` | Конечная точка API Gemini | https://generativelanguage.googleapis.com/v1beta/models |
| `GROQ_API_KEY` | API-ключ Groq | - |
| `GROQ_MODELS` | Модели Groq для использования (разделенные запятыми) | - |
| `MAX_HISTORY_LENGTH` | Максимальная длина истории | 50 |
| `CLAUDE_API_KEY` | API-ключ Anthropic Claude | - |
| `CLAUDE_MODELS` | Модели Claude для использования (разделенные запятыми) | - |
| `CLAUDE_ENDPOINT` | Конечная точка API Claude | https://api.anthropic.com/v1/chat/completions |

Убедитесь, что добавили эти переменные окружения в конфигурацию окружения вашего проекта при развертывании на Vercel или других платформах.

## Руководство по использованию 📖

- `/start` - Инициализировать бота
- `/new` - Начать новый разговор
- `/history` - Просмотреть краткое изложение истории разговоров
- `/help` - Получить справочную информацию
- `/switchmodel <название модели>` - Переключить модель ИИ
- `/img <описание> [размер]` - Сгенерировать изображение
- `/language <код языка>` - Переключить язык интерфейса
- Отправьте изображение для анализа
- Отправьте сообщение напрямую для разговора

Поддерживаемые языки (используйте команду /language):
- Английский (en)
- Упрощенный китайский (zh-cn)
- Традиционный китайский (zh-hant)
- Японский (ja)
- Испанский (es)
- Французский (fr)
- Русский (ru)
- Немецкий (de)

## Примечания ⚠️

- Разумно используйте квоты API, особенно при использовании функций изображений 💸
- Надежно храните переменные окружения и API-ключи 🔒
- Разные модели ИИ могут иметь разные характеристики и ограничения 🔄
- Регулярно проверяйте и обновляйте зависимости для обеспечения безопасности и производительности 🔧

## Вклад в проект 🤝

Приветствуются Pull Request'ы или открытие Issues для улучшения этого проекта! Ваш вклад сделает этого ИИ-ассистента более мощным и интересным.

## Лицензия 📜

Этот проект лицензирован под [лицензией MIT](https://choosealicense.com/licenses/mit/).

---

О кнопке "Развернуть с Vercel":
Эта кнопка предоставляет функцию развертывания в один клик на Vercel, что очень удобно. Однако, обратите внимание:

1. Ссылка в кнопке указывает на оригинальный репозиторий (https://github.com/OrganizationOrganizationOrganization/GPT-Telegram-Bot).
2. Если вы сделали форк этого проекта и хотите развернуть свою собственную версию, вам нужно обновить эту ссылку кнопки в README.
3. Метод обновления: Замените `OrganizationOrganizationOrganization` в ссылке на ваше имя пользователя GitHub и название репозитория.

Например, если ваше имя пользователя GitHub "vashimya", вы должны изменить ссылку кнопки на:

```markdown
[![Развернуть с Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=[![Развернуть с Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/OrganizationOrganizationOrganization/GPT-Telegram-Bot))
```

Это обеспечит, что кнопка "Развернуть с Vercel" будет развертывать вашу форкнутую версию, а не оригинальный репозиторий.
