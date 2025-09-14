# Инструкции по развертыванию в GitHub

## Загрузка в ваш репозиторий

### Шаг 1: Инициализация Git
```bash
cd telegram-story-app
git init
```

### Шаг 2: Добавление файлов
```bash
git add .
```

### Шаг 3: Первый коммит
```bash
git commit -m "Initial commit: Telegram Mini App - Полночное Кафе"
```

### Шаг 4: Подключение к вашему репозиторию
```bash
git remote add origin https://github.com/kartermaster/niprostit.git
```

### Шаг 5: Загрузка в GitHub
```bash
git branch -M main
git push -u origin main
```

## Альтернативный способ (через GitHub Desktop)

1. Откройте GitHub Desktop
2. Выберите "Add an Existing Repository from your Hard Drive"
3. Выберите папку `telegram-story-app`
4. Нажмите "Publish repository"
5. Выберите ваш аккаунт и репозиторий `niprostit`

## Настройка GitHub Pages для демо

### Вариант 1: GitHub Actions (рекомендуется)

1. Создайте файл `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '18'
          cache: 'npm'
          
      - name: Install dependencies
        run: npm ci
        
      - name: Build
        run: npm run build
        
      - name: Setup Pages
        uses: actions/configure-pages@v4
        
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: './dist'
          
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### Вариант 2: Простая настройка

1. В настройках репозитория перейдите в "Pages"
2. В "Source" выберите "GitHub Actions"
3. Создайте файл `.github/workflows/deploy.yml` (как выше)
4. После пуша приложение будет доступно по адресу:
   `https://kartermaster.github.io/niprostit/`

## Настройка Telegram Bot

1. Создайте бота через [@BotFather](https://t.me/botfather):
   ```
   /newbot
   Имя: Полночное Кафе
   Username: midnight_cafe_bot
   ```

2. Настройте Mini App:
   ```
   /newapp
   Выберите вашего бота
   App title: Полночное Кафе
   App description: Интерактивная романтическая история
   App photo: Загрузите скриншот
   App URL: https://kartermaster.github.io/niprostit/
   ```

3. Получите ссылку для запуска Mini App

## Тестирование

### Локальное тестирование
```bash
npm run dev
```
Откройте http://localhost:3000

### Тестирование в Telegram
1. Найдите вашего бота в Telegram
2. Отправьте команду `/start`
3. Нажмите на кнопку Mini App или отправьте ссылку

## Структура файлов для загрузки

Убедитесь, что в репозитории есть все необходимые файлы:

```
niprostit/
├── src/
│   ├── components/
│   ├── contexts/
│   ├── data/
│   ├── hooks/
│   ├── services/
│   ├── types/
│   ├── App.tsx
│   ├── App.css
│   ├── index.css
│   └── main.tsx
├── public/
├── package.json
├── vite.config.ts
├── tsconfig.json
├── index.html
├── README.md
└── .gitignore
```

## Полезные команды

### Обновление репозитория
```bash
git add .
git commit -m "Update: описание изменений"
git push origin main
```

### Сборка для продакшена
```bash
npm run build
# Файлы в папке dist готовы для развертывания
```

### Предварительный просмотр сборки
```bash
npm run preview
```

## Возможные проблемы

### Если git push не работает:
1. Проверьте, что вы авторизованы в GitHub
2. Убедитесь, что репозиторий существует
3. Попробуйте использовать SSH вместо HTTPS

### Если Mini App не загружается:
1. Проверьте, что GitHub Pages включен
2. Убедитесь, что URL правильный
3. Проверьте консоль браузера на ошибки

## Дополнительные возможности

### Настройка домена
1. В настройках репозитория добавьте custom domain
2. Настройте DNS записи
3. Обновите URL в Telegram Bot

### Аналитика
Добавьте Google Analytics или Yandex Metrica для отслеживания пользователей.

### Обновления
Для обновления приложения просто сделайте push в main ветку - GitHub Actions автоматически пересоберет и развернет новую версию.
