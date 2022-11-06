# Optimus post
### Описание модели

#### Для определения популярности точки потенциального расположения постаматов наша модель учитывает следующие данные:
- количество географических объектов различных типов в окружности радиусом 100м,</br>а также в кольцах окружности радиусами 100м-200м, 200м-400м и 400м-800м (800м ~ 10мин ходьбы);
- транспортный и пешеходный трафик (пока для одного района).

#### Группы рассматриваемых объектов (подробнее о типах см. в файле `./notebooks-model/geo-objects.txt`):
- жилые дома
- места активного отдыха
- культурные и развлекательные места
- торговые объекты
- услуги
- пункты здоровья
- детские сады
- образовательные учреждения
- пункты питания
- места общественного транспорта
- прочие транспортные объекты
- места работы и проживания
- религиозные пункты

#### [Ссылка на репозиторий backend'а](https://github.com/NoobyTheTurtle/optimus-post-api)
#### [Ссылка на репозиторий frontend'а](https://github.com/mangupli/optimus-post-interface)

### Инициализация проекта
1. [Установите](https://www.docker.com/) `docker` и `docker compose`
2. Клонируйте данный репозиторий и его sub-репозитории
   * `git clone --recurse-submodules https://github.com/NoobyTheTurtle/optimus-post.git`
3. Иницализируем `env` переменные `./optimus-post.sh init_env`
4. В файле `./api/.env` заполняем:
   * `POSTGRES_PASSWORD, PGPASSWORD` - пароль для базы данных
   * `DATABASE_PASSWORD` - пароль приложения для базы данных
   * `API_KEY_MOS_RU` - API ключ для mos.ru (Необязательно)
5. Запускаем сборку проекта `./optimus-post.sh start`
6. Ждём 🙄
7. Запускаем создание базы данных `./optimus-post.sh init_db <пароль приложения для базы данных>`
8. Вводим пароль для базы данных
9. Запускаем создание заготовленных Округов и Районов (Wikipedia, API2gis) `./optimus-post.sh seed`
10. Приложение запущено
   * `http://localhost/` - Главная страница
   * `http://localhost:3000/api-docs/index.html` - Документация к API (Swagger)
   * `http://localhost:3000/sidekiq/` - Страница управления фоновами задачами

#### Запуск проекта `./optimus-post.sh start`

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
### [Ссылка на макет](https://www.figma.com/file/Y1n6e4PtagPXHznwegUPa8/Optimus-Post?node-id=0%3A1)

#### Алгоритм подсчета трафика находится в папке notebooks-mos-traffic

### Технологии
- Rails / Ruby (Backend)
- React / JS (Frontend)
- PostgreSQL (Backend DB)
- Sidekiq (Background processing)
- Redis (Background processing DB)
- Rspec / Rswag (Tests, Swagger)
- Python / LightGBM (Model)

