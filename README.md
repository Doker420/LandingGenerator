# LandingGenerator
✅ – every page is unique and every website uses different technologies ・ Beautiful, modern design 🎨 – like a real website! ・ Multiple SEO-optimized pages with navigation 📄 ・ Custom privacy policy &amp; terms 📝 – no more legal headaches! ・ ZIP download with all files 📦 – ready to use! ・ Lightning-fast generation ⚡️ – forget about waiting for hours!

# 🤖 Telegram-Бот для генерации лендингов

👉 **Ссылка на бота:** [Landing Generator Bot](https://t.me/Landing_generatorAiBot)

Бот полностью функционален и включает все запланированные возможности!

## 📂 Структура проекта

```
landing_bot/
├── bot.py
├── config.py
├── database.py
├── arena_generator.py
├── admin.py
├── requirements.txt
└── cookies/
    └── arena_cookies.json
├── generated/
    └── (генерируемые лендинги)
└─ .env.example
```

## 🔧 Установка

1. **Установка зависимостей**

```bash
pip install -r requirements.txt
```

2. **Установка Playwright браузеров**

```bash
playwright install chromium
playwright install-deps
```

3. **Создание директорий**

```bash
mkdir -p cookies generated
```

4. **Настройка .env**

Скопируйте `.env.example` и заполните токен бота и ID администраторов:
```env
BOT_TOKEN=your_bot_token_here
ADMIN_IDS=123456789,987654321
```

5. **Настройка cookies Arena.ai**

- Войдите на [arena.ai](https://arena.ai) через браузер
- Нажмите F12 → Application → Local Storage → Cookies → [arena.ai]
- Экспортируйте cookies в `cookies/arena_cookies.json`
- Альтернативно используйте расширение для экспорта cookies

6. **Запуск бота**

```bash
python bot.py
```

## 🚀 Запуск через systemd (Ubuntu)

Создайте службу:

```ini
# /etc/systemd/system/landing-bot.service
[Unit]
Description=Landing Generator Telegram Bot
After=network.target

[Service]
Type=simple
User=your_user
WorkingDirectory=/path/to/landing_bot
Environment="PATH=/path/to/landing_bot/venv/bin"
ExecStart=/path/to/landing_bot/venv/bin/python bot.py
Restart=always

[Install]
WantedBy=multi-user.target
```

Запустите сервис:

```bash
sudo systemctl daemon-reload
sudo systemctl enable landing-bot
sudo systemctl start landing-bot
sudo systemctl status landing-bot
```

## 🔐 Функционал

- **Генерация лендингов**
- **Реферальная программа**: привилегии за приглашённых друзей + бонусы
- **Промокоды**: активация дополнительных генераций
- **Админ-панель**: статистика, создание промокодов, рассылка
- **Многоязычная поддержка**
- **База данных** для хранения пользователей, сессий, промокодов

## 🛠 Техническая информация

- **Архитектура**: модульный дизайн с разделением ответственности
- **База данных**: SQLite через aiosqlite (асинхронный)
- **Обработка браузера**: Playwright с сохранением cookies
- **Обработка сообщений**: модульный обработчик с отдельными состояниями
- **Обработка ошибок**: централизованный обработчик с логированием

## ⚠ Важно!

1. Дляnormal operation необходимо экспортировать cookies из браузера
2. При первом запуске бот автоматически создаст базу данных
3. Все комбинации сгенерированных лендингов сохраняются в папке `/generated`
4. Для коммерческого использования необходимо оформить лицензию
