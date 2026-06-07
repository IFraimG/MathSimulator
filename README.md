# MathSimulator

Математический тренажер для решения математических примеров 9 класса с элементами геймификации и историей прохождения.

## Технологии

### Frontend
- TypeScript
- React 17
- Redux + Redux Toolkit + Redux Thunk
- React Router DOM
- Material UI (v4)
- SCSS
- Axios
- Vite

### Backend
- TypeScript
- NestJS
- MongoDB (MongoDB Atlas)
- Mongoose
- Passport.js (JWT + Local Strategy)
- bcrypt
- dotenv
- Jest

## Архитектурные решения

### Модульная архитектура NestJS
Бэкенд разбит на независимые модули: `UsersModule`, `AuthModule`, `TasksModule`, `FileModule`. Каждый модуль инкапсулирует свой контроллер, сервис и Mongoose-схему.

### JWT-аутентификация через Passport.js
Безопасность API реализована через стратегии Passport: `passport-local` для логина по email/паролю и `passport-jwt` для защиты остальных эндпоинтов. Пароли хранятся в хэшированном виде через `bcrypt`.

### Express.js для SSR-обёртки фронтенд-приложения
Фронтенд собирается Vite в статику и раздаётся через минималистичный Express-сервер (`server.js`) для корректной работы html-роутинга при прямых переходах по URL без реализации полноценного Server Side Rendering.
