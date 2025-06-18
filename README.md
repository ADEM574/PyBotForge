## 🧱 PyBotForge

**PyBotForge** — это базовый шаблон для Telegram-ботов на Python (pyTelegramBotAPI).<br>
Позволяет быстро начать разработку, не тратя время на структуру, подключение токена, клавиатур и баз данных.

---

## 🚀 Возможности шаблона

* Чистая и логичная структура проекта (в стиле Django).
* Поддержка переменных окружения `.env`.
* Хранение пользователей в SQLite.
* Модульные обработчики команд.
* Готов к расширению под любую задачу: от бизнес-бота до MVP.

---

## 📦 Стек технологий

| Компонент        | Описание                                                       |
| ---------------- | -------------------------------------------------------------- |
| Telegram API     | [pyTelegramBotAPI](https://pypi.org/project/pyTelegramBotAPI/) |
| Переменные среды | [python-dotenv](https://pypi.org/project/python-dotenv/)       |
| База данных      | SQLite (`sqlite3` из стандартной библиотеки)                   |

---

## 📁 Структура проекта

```bash
PyBotForge/
├── db/                # Работа с БД
│   ├── __init__.py
│   └── users.db       # Хранилище Telegram ID пользователей
├── handlers/          # Обработчики команд
│   ├── __init__.py
│   └── start.py       # /start — приветствие и добавление пользователя в БД
├── utils/             # Вспомогательные функции
│   └── __init__.py
├── .env               # Переменные окружения (токен и т.д.)
├── bot.py             # Точка входа: запуск бота
├── config.py          # Загрузка и хранение конфигураций из .env
└── keyboards.py       # Клавиатуры (Reply / Inline)
```

---

## 🛠 Установка и запуск

### 1. Склонируйте проект:

```bash
git clone https://github.com/Artemy-dev/PyBotForge.git
cd PyBotForge
```

### 2. (Опционально) Сделайте из шаблона новый проект:

```bash
rm -rf .git
git init
git add .
git commit -m "initial commit"
```

### 3. Установите зависимости:

```bash
pip install pyTelegramBotAPI python-dotenv
```

### 4. Укажите токен бота

Создайте файл `.env` (если не существует) и добавьте туда:

```
BOT_TOKEN=your_telegram_token_here
```

### 5. Запустите бота:

```bash
python bot.py
```

Если всё настроено правильно, бот напишет в консоль:

```
Bot is polling...
```

---

## 🧩 Что делает `/start`

* Отправляет приветствие пользователю.
* Добавляет Telegram ID пользователя в базу `users.db`, если его там ещё нет.

---

## 📌 Расширение

Создавайте свои обработчики в папке `handlers/`, например `menu.py`, `admin.py`, и регистрируйте их в `bot.py`:

```python
from handlers import menu
menu.register_handlers(bot)
```

---

## 🧠 Автор

Разработано [Artemy-dev](https://github.com/Artemy-dev)<br>
📬 Telegram: [@Artemy\_Develop](https://t.me/Artemy_Develop)

---
