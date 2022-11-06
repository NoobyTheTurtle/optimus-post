# Optimus post
### Описание
- _Лучшее_ 
- _Описание_

#### [Ссылка на проект backend'а](https://github.com/NoobyTheTurtle/optimus-post-api)
#### [Ссылка на проект frontend'а](https://github.com/mangupli/optimus-post-interface)

### Первый запуск проекта
1. Установите `docker` и `docker compose` [ссылка](https://www.docker.com/)
2. Клонируйте данный репозиторий к себе
3. Иницализируем `env` переменные `./optimus-post.sh init_env`
4. В файле `./api/.env` заполняем недостающие переменные
   * `POSTGRES_PASSWORD, PGPASSWORD` - пароль для базы данных
   * `DATABASE_PASSWORD` - пароль приложения для базы данных
   * `API_KEY_MOS_RU` - API ключ для mos.ru
5. Запускаем сборку проекта `./optimus-post.sh start`
6. Ждём
7. Запускаем создание базы данных `./optimus-post.sh init_db "пароль приложения для базы данных"` (скрипт потребует ввести пароль для базы данных)
8. Запускаем создание заготовленных данных `./optimus-post.sh seed`
9. Приложение запущено
   * `http://localhost/` - Сайт
   * `http://localhost:3000/api-docs/index.html` - Документация к API (Swagger)
   * `http://localhost:3000/sidekiq/` - Страница управления фоновами задачами

### Запуск проект `./optimus-post.sh start`

### Вспомогательные команды
* Запустить тесты `./optimus-post.sh rspec`.
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
### [Ссылка на документацию к API](http://188.72.109.162:3000/api-docs/index.html)

### Технологии
- Rails / Ruby (Backend)
- React / JS (Frontend)
- PostgreSQL (Backend DB)
- Sidekiq (Background processing)
- Redis (Background processing DB)
- Rspec/Rswag (Tests/Swagger)

