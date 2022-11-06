# Optimus post
### Описание
- _Лучшее_ 
- _Описание_

### Запуск проекта
1. Установите `docker` и `docker compose`
2. Клонируйте данный репозиторий к себе
3. Переходим в папку с api `cd api`
4. Копируем `env` переменные: `cat .env.example > .env` и заполняем недостающие переменные
   * `POSTGRES_PASSWORD, PGPASSWORD` - пароль для базы данных
   * `DATABASE_PASSWORD` - пароль приложения для базы данных
   * `API_KEY_MOS_RU` - api ключ для mos.ru
5. Переходим в папку с front `cd ../front` и копируем `env` переменные: `cat .env.example > .env`
6. Возвращаемся в корневую папку `cd ..`
7. Запускаем сборку проекта `./optimus-post.sh start`
8. Ждём
9. Запускаем создание базы данных `./optimus-post.sh init_db "пароль приложения для базы данных"` (скрипт потребует ввести пароль для базы данных)
10. Запускаем создание заготовленных данных `./optimus-post.sh seed`
11. Приложение запущено
   * `http://localhost/` - Сайт
   * `http://localhost:3000/api-docs/index.html` - Документация к API (Swagger)
   * `http://localhost:3000/sidekiq/` - Страница управления фоновами задачами
---
* Rspec-тесты запускаются через `./optimus-post.sh rspec`.
* Пересгенирировать документацию к API `./optimus-post.sh swagger`.
* Прогнать миграции `./optimus-post.sh migrate`.
* Пересобрать контейнеры `./optimus-post.sh build`.
* Зайти в консоль бэкенда `./optimus-post.sh console`.
* Зайти в контейнер бэкенда `./optimus-post.sh connect`.
* Создать дамп базы в ./dump.sql `./optimus-post.sh dump`.
* Остановить контейнеры `./optimus-post.sh stop`.
* Удалить контейнеры `./optimus-post.sh rmi`.
* Запустить проект `./optimus-post.sh start`.

### [Ссылка на проект](http://188.72.109.162/)

### Технологии
- Rails / Ruby (Backend)
- React / JS (Frontend)
- PostgreSQL (Backend DB)
- Sidekiq (Background processing)
- Redis (Background processing DB)
- Rspec/Rswag (Tests/Swagger)

