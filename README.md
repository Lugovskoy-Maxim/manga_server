# Manga Server

Веб-сервер для чтения манги с системой пользователей и закладок.

## 🛠 Технологии

- **Backend**: NestJS, TypeScript
- **Database**: MongoDB с Mongoose
- **Authentication**: JWT, bcrypt
- **File Upload**: Multer
- **Validation**: class-validator, class-transformer

## 🚀 Функционал

### 👥 Пользователи
- Регистрация и авторизация (JWT)
- Профиль с закладками и историей чтения
- Система ролей

### 📚 Тайтлы (Манга)
- CRUD операции для манги
- Поиск и фильтрация по жанрам/статусу
- Пагинация и сортировка
- Рейтинги и просмотры

### 📖 Главы
- Создание глав с загрузкой изображений
- Навигация между главами
- Статистика просмотров
- Автоматическое обновление счетчика глав в тайтлах

### 🔖 Закладки и история
- Добавление/удаление закладок
- История чтения
- Статистика пользователя

## 🎯 API Endpoints

### Аутентификация
- `POST /auth/register` - Регистрация
- `POST /auth/login` - Вход

### Тайтлы
- `GET /titles` - Список с пагинацией
- `POST /titles` - Создание тайтла
- `GET /titles/:id` - Получить тайтл
- `PATCH /titles/:id` - Обновить тайтл

### Главы
- `POST /chapters/upload` - Создание главы с файлами
- `GET /chapters/title/:titleId` - Главы тайтла
- `POST /chapters/:id/view` - Увеличить просмотры

### Пользователи
- `GET /users/:id/bookmarks` - Закладки пользователя
- `POST /users/:id/bookmarks` - Добавить закладку

## 🏃‍♂️ Быстрый старт

1. **Установка зависимостей**
   ```bash
      npm install

2. **Запуск MongoDB**
    ```bash
      docker-compose up -d  
3. **Настройка окружения**
   ```
      MONGO_LOGIN=admin
      MONGO_PASSWORD=password123
      MONGO_HOST=localhost
      MONGO_PORT=27017
      MONGO_AUTHDATABASE=admin
      JWT_SECRET=your-secret-key
4. **Запуск приложения**
    ```bash
      npm run start:dev

### Структура проекта
  ```bash
      src/
      ├── auth/          # Аутентификация
      ├── users/         # Пользователи
      ├── titles/        # Тайтлы манги  
      ├── chapters/      # Главы
      ├── files/         # Работа с файлами
      └── schemas/       # MongoDB схемы