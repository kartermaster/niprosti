# 🚀 Загрузка в ваш репозиторий GitHub

## Ваш репозиторий: https://github.com/kartermaster/niprostit

### Способ 1: Через командную строку (рекомендуется)

1. **Откройте PowerShell или Command Prompt**

2. **Перейдите в папку с проектом:**
   ```bash
   cd "D:\Nik\Cursor\First project\telegram-story-app"
   ```

3. **Инициализируйте Git:**
   ```bash
   git init
   ```

4. **Добавьте все файлы:**
   ```bash
   git add .
   ```

5. **Сделайте первый коммит:**
   ```bash
   git commit -m "Initial commit: Telegram Mini App - Полночное Кафе"
   ```

6. **Подключите ваш репозиторий:**
   ```bash
   git remote add origin https://github.com/kartermaster/niprostit.git
   ```

7. **Загрузите в GitHub:**
   ```bash
   git branch -M main
   git push -u origin main
   ```

### Способ 2: Через GitHub Desktop

1. **Скачайте GitHub Desktop** (если нет): https://desktop.github.com/

2. **Откройте GitHub Desktop**

3. **Выберите "Add an Existing Repository from your Hard Drive"**

4. **Выберите папку:** `D:\Nik\Cursor\First project\telegram-story-app`

5. **Нажмите "Publish repository"**

6. **Выберите:**
   - Owner: kartermaster
   - Name: niprostit
   - Description: Интерактивная романтическая история для Telegram Mini App

7. **Нажмите "Publish Repository"**

### Способ 3: Через веб-интерфейс GitHub

1. **Откройте ваш репозиторий:** https://github.com/kartermaster/niprostit

2. **Нажмите "uploading an existing file"**

3. **Перетащите все файлы из папки** `telegram-story-app` в репозиторий

4. **Добавьте коммит:**
   - Commit message: "Initial commit: Telegram Mini App - Полночное Кафе"

5. **Нажмите "Commit changes"**

## 🔧 Настройка GitHub Pages

После загрузки кода:

1. **Перейдите в Settings вашего репозитория**

2. **Найдите раздел "Pages" в левом меню**

3. **В "Source" выберите "GitHub Actions"**

4. **Файл `.github/workflows/deploy.yml` уже создан и автоматически настроит развертывание**

5. **Ваше приложение будет доступно по адресу:**
   ```
   https://kartermaster.github.io/niprostit/
   ```

## 🤖 Настройка Telegram Bot

### Создание бота:

1. **Найдите @BotFather в Telegram**

2. **Отправьте команды:**
   ```
   /newbot
   ```

3. **Введите данные:**
   - **Bot name:** Полночное Кафе
   - **Username:** midnight_cafe_story_bot (или любой свободный)

4. **Сохраните токен бота**

### Настройка Mini App:

1. **Отправьте BotFather:**
   ```
   /newapp
   ```

2. **Выберите вашего бота**

3. **Заполните данные:**
   - **App title:** Полночное Кафе
   - **App description:** Интерактивная романтическая история с 4 различными финалами
   - **App photo:** Загрузите скриншот игры
   - **App URL:** https://kartermaster.github.io/niprostit/

4. **Получите ссылку для запуска Mini App**

## 📱 Тестирование

### Локальное тестирование:
```bash
cd "D:\Nik\Cursor\First project\telegram-story-app"
npm install
npm run dev
```

### Тестирование в Telegram:
1. Найдите вашего бота в Telegram
2. Отправьте `/start`
3. Нажмите на кнопку Mini App

## 📁 Структура загружаемых файлов

Убедитесь, что загружаете все эти файлы:

```
telegram-story-app/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── src/
│   ├── components/
│   │   ├── Scene.tsx
│   │   ├── Scene.css
│   │   ├── ChoiceButton.tsx
│   │   ├── ChoiceButton.css
│   │   └── ProgressIndicator.tsx
│   ├── contexts/
│   │   └── StoryContext.tsx
│   ├── data/
│   │   └── storyData.ts
│   ├── hooks/
│   │   └── useTelegram.ts
│   ├── services/
│   │   └── telegramService.ts
│   ├── types/
│   │   └── index.ts
│   ├── App.tsx
│   ├── App.css
│   ├── index.css
│   └── main.tsx
├── .gitignore
├── DEPLOYMENT.md
├── GITHUB_UPLOAD.md
├── README.md
├── index.html
├── package.json
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

## 🎯 Что получится

После выполнения всех шагов:

1. ✅ **Код в GitHub:** https://github.com/kartermaster/niprostit
2. ✅ **Рабочее приложение:** https://kartermaster.github.io/niprostit/
3. ✅ **Telegram Bot** с Mini App
4. ✅ **Автоматическое развертывание** при обновлениях

## 🔄 Обновления

Для обновления приложения:
```bash
git add .
git commit -m "Update: описание изменений"
git push origin main
```

GitHub Actions автоматически пересоберет и развернет новую версию.

## ❓ Помощь

Если что-то не работает:

1. **Проверьте, что все файлы загружены**
2. **Убедитесь, что GitHub Pages включен**
3. **Проверьте Actions в репозитории на ошибки**
4. **Убедитесь, что URL в Telegram Bot правильный**

**Удачи с вашим проектом! 🚀**
