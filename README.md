# CyberCats VPN

Сервис по продаже конфигураций VLESS VPN с уникальной стилистикой киберкотов в 8-битном стиле.

## Компоненты проекта

1. **Лендинг**: Веб-сайт на Next.js с информацией о сервисе.
2. **Telegram-бот**: Основной интерфейс для покупки и управления VPN.
3. **Административная панель**: Для мониторинга и управления системой.
4. **VPN-сервис**: Система для создания и управления VLESS-конфигурациями.

## Технологический стек

- **Бэкенд**: Node.js, TypeScript, NestJS
- **База данных**: MongoDB
- **Кэширование**: Redis
- **Фронтенд**: Next.js, Tailwind CSS, Framer Motion
- **Телеграм-бот**: Node.js, Telegraf.js
- **VPN**: xray-core (VLESS)
- **Контейнеризация**: Docker
- **CI/CD**: GitHub Actions
- **Мониторинг**: Prometheus, Grafana

## Требования для установки

- Node.js 16+
- MongoDB 4.4+
- Redis 6+
- Docker (опционально)
- Токен Telegram-бота (получить у [@BotFather](https://t.me/BotFather))

## Установка и запуск

### 1. Клонирование репозитория

```bash
git clone https://github.com/CAHEK2005/cybercats-vpn.git
cd cybercats-vpn
```

### 2. Установка зависимостей

```bash
# Установка зависимостей основного проекта
npm install

# Установка зависимостей лендинга
cd cybercats-landing
npm install
cd ..
```

### 3. Настройка переменных окружения

Создайте файл `.env` в корне проекта со следующими переменными:

```
# Telegram Bot Settings
BOT_TOKEN=your_telegram_bot_token_here
ADMIN_BOT_TOKEN=your_admin_bot_token_here

# MongoDB Settings
MONGO_URI=mongodb://localhost:27017/cybercats_vpn

# Admin Panel Settings
ADMIN_PORT=3001
JWT_SECRET=your_jwt_secret_key_here

# Payment API Keys
CRYPTO_API_KEY=your_crypto_api_key_here
CARD_API_KEY=your_card_api_key_here
SBP_API_KEY=your_sbp_api_key_here

# Other Settings
NODE_ENV=development
```

### 4. Сборка проекта

```bash
# Сборка основного проекта
npm run build

# Сборка лендинга
cd cybercats-landing
npm run build
cd ..
```

### 5. Запуск проекта

#### Для разработки:

```bash
# Запуск всего проекта в режиме разработки
npm run dev

# Запуск только Telegram-бота
npm run bot

# Запуск только административной панели
npm run admin

# Запуск только лендинга
npm run landing
```

#### Для продакшена:

```bash
# Запуск всего проекта
npm start
```

### 6. Запуск с использованием Docker (опционально)

```bash
# Сборка Docker-образа
docker-compose build

# Запуск контейнеров
docker-compose up -d
```

## Структура проекта

```
cybercats-vpn/
├── src/
│   ├── bot/           # Код Telegram-бота
│   ├── admin/         # Код административной панели
│   └── index.ts       # Точка входа
├── cybercats-landing/ # Код лендинга
├── data/              # Данные и конфигурации
├── dist/              # Скомпилированный код
├── .env               # Переменные окружения
└── package.json
```

## Администрирование

Доступ к админ-панели осуществляется по адресу `http://localhost:3001` (или другому порту, указанному в настройках).

Логин/пароль по умолчанию:
- **Admin**: admin / admin123
- **Support**: support / support123

## Дополнительная информация

- Для обработки платежей требуется настройка API-ключей платежных систем
- Для работы VPN требуется настройка серверов с установленным xray-core
- Для полноценной работы реферальной программы необходимо настроить уведомления

## Лицензия

MIT
